---
description: >-
  This page describes how to handle various things related to client-server
  communications. This includes sending messages, implementing prediction, etc.
---

# Client-Server communications

Core Keeper is a server authoritative game. This means for an action to occur, the server must be aware of it and approve. When we write mods we must be able to create logic that allows for Client-Server communication to occur.

{% hint style="info" %}
Note that Unity uses extensive code gen to implement features outlined here. If you ever get errors regarding CodeGen ensure your mod output Scripts folder has Generated folder. If it doesn't your Unity project might have an error. A restart usually helps

Additionally you might want to utilize Burst
{% endhint %}

## Ghost Components

Ghost component is one of the simplest ways to transfer data between Client and server. In its essence Ghost Component is just a normal ECS component that is synced over network.

To make a Ghost Component first Create IComponentData deriving ECS component:

<pre class="language-csharp"><code class="lang-csharp"><strong>public struct ExampleCD : IComponentData
</strong>{
    public int importantField;
    
    public float normalField;
}
</code></pre>

To make this component a Ghost Component all you have to do is add a `GhostComponent` attribute to it. Additionally you must mark every field you want to be synced with `GhostField` attribute:

<pre class="language-csharp"><code class="lang-csharp">[GhostComponent]
<strong>public struct ExampleCD : IComponentData
</strong>{
    // This field will end up synced
    [GhostField] 
    public int importantField;
    
    // This field isn't marked, so it won't be synced
    public float normalField;
}
</code></pre>

Making Ghost Components is just as easy as this. Now any data set to this component of the server will be automatically replicated to all clients. Refer to [this](https://docs.unity3d.com/Packages/com.unity.netcode@1.0/manual/ghost-snapshots.html#replicating-components-and-buffers) guide to learn more

## Remote Procedure Calls

Remote Procedure Calls (or RPC's) are a way to send information to the Server or clients in one-shot manner. They allow you to send arbitrary data or commands to the other side, be it requests or data

This example will focus on Client to Server communication, as that is the most common scenario, however you can send RPC from Server to Clients or even both ways

To make a RPC first add RPC command data definition:

```csharp
public enum MyModCommandType : byte
{
    UNDEFINED,
    DO_VERY_IMPORTANT_THING,
    ANOTHER_IMPORTANT_TASK
    
    //etc
}

public struct MyModCommandRPC : IRpcCommand
{
    // This enum will define what kind of command this is
    public MyModCommandType commandType;
    
    // This is bundled request data.
    // This can be target entities, such as players
    // Or any other neccessary data
    public Entity entity0;
    public int value;
    
    // you can add more fields as needed
}
```

Now define two systems. One for Clients:

```csharp
[UpdateInGroup(typeof(RunSimulationSystemGroup))]
[WorldSystemFilter(WorldSystemFilterFlags.ClientSimulation)]
public partial class ClientModCommandSystem : PugSimulationSystemBase
{
    private NativeQueue<MyModCommandRPC> rpcQueue;
    private EntityArchetype rpcArchetype;

    protected override void OnCreate()
    {
        UpdatesInRunGroup();
        rpcQueue = new NativeQueue<MyModCommandRPC>(Allocator.Persistent);
        rpcArchetype = EntityManager.CreateArchetype(typeof(MyModCommandRPC), typeof(SendRpcCommandRequest));

        base.OnCreate();
    }

    #region Commands

    // This is the most important section
    // Here you can make send functions to have 
    // easy interface with the rest of your code
    public void DoVeryImportantThing(Entity target, int value)
    {
        rpcQueue.Enqueue(new MyModCommandRPC()
        {
            commandType = MyModCommandType.DO_VERY_IMPORTANT_THING,
            entity0 = target,
            value = value
        });
    }

    #endregion

    protected override void OnUpdate()
    {
        EntityCommandBuffer entityCommandBuffer = CreateCommandBuffer();
        while (rpcQueue.TryDequeue(out MyModCommandRPC component))
        {
            Entity e = entityCommandBuffer.CreateEntity(rpcArchetype);
            entityCommandBuffer.SetComponent(e, component);
        }
    }
}
```

And one for Server:

```csharp
[UpdateInGroup(typeof(SimulationSystemGroup))]
[WorldSystemFilter(WorldSystemFilterFlags.ServerSimulation)]
public partial class ServerModCommandSystem : PugSimulationSystemBase
{
    protected override void OnUpdate()
    {
        var ecb = CreateCommandBuffer();

        Entities.ForEach((Entity rpcEntity, in MyModCommandRPC rpc, in ReceiveRpcCommandRequest req) =>
            {
                switch (rpc.commandType)
                {
                    case MyModCommandType.DO_VERY_IMPORTANT_THING:

                        // Do very important thing
                        // This code will be executed on the server
                        break;
                }
                ecb.DestroyEntity(rpcEntity);
            })
            .WithoutBurst()
            .Schedule();

        base.OnUpdate();
    }
}
```

Now to use these systems you just have to add this code in your IMod class:

```csharp
public static ClientModCommandSystem clientSystem;

// You might already have this method
// if so, just add method body to your code
public void EarlyInit() 
{
    API.Client.OnWorldCreated += ClientWorldReady;
}

private static void ClientWorldReady()
{
    var world = API.Client.World;
    clientSystem = world.GetOrCreateSystemManaged<ClientModCommandSystem>();
}
```

Now you can use `MyMod.clientSystem.DoVeryImportantThing()` from anywhere in your code

## Prediction

This guide has not been written yet! If you know how to do this, [add it](../../how-to-contribute.md)!
