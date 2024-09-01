# Technologies and Tools

This game is using a few tools that are important to understand while modding. Specifically these are DOTS, ECS, Jobs system and Burst

## Unity concepts

### Game Object

Game Object represents anything which can exist in a **Scene**. Please note that in Core Keeper only graphical prefabs and UI uses Game Objects at runtime. Players, placeables and enemies are NOT Game Objects, they are ECS Entities.

### Mono Behaviour

Mono Behaviour is a class that can be attached to Game Objects. This component can give Game Objects behaviour.

### Scriptable Object

A data container that you can use to save large amounts of data. Scriptable objects live outside of scenes and can be accessed by any code. In this game many lookup tables are stored as Scriptable Objects. Another notable Scriptable object are Sprite Assets.

## DOTS

**Data-Oriented Technology Stack** (DOTS) is a feature of Unity, which is currently in pre release. It uses completely different way of thinking about game state than usual Game Object based approach.&#x20;

With DOTS also come ECS, Job Systems and Burst.

### ECS

Entity Component System (ECS) is the main package for DOTS. It provides the core feature of DOTS: Entities, Components and Systems

Entities are containers for many Components. The class itself is just a identifier into the ECS state.

Components are structs, which hold component data. However they don't hold any behavior.

Systems hold the actual behavior. They can perform operations of group of components in bulk, utilizing Job Systems and Burst to do so in multi-threaded way

If you are struggling to understand ECS, try [this info-graphic](https://www.reddit.com/r/Unity3D/comments/y6elrw/what\_is\_ecs\_an\_infographic\_to\_understand\_the/) or [this video](https://www.youtube.com/watch?v=71RSWVyOMEY).

Limoka has created an overview of the game's ECS components on mod.io, although it may be out of date: [https://mod.io/g/corekeeper/r/ecs-component-compendium](https://mod.io/g/corekeeper/r/ecs-component-compendium)

#### Authoring

When making the game and it's prefabs, devs are using Hybrid system, which allows to **author** the content using typical game objects and MonoBehavior based components.

After the game is loaded each Authoring component performs conversion from game object world to ECS world and ECS components.

### Job Systems

Jobs are the way devs write system behavior which allows to easy multi-threading.&#x20;

Unfortunately for us, we can't create custom Jobs. And patching such jobs also currently poses an issue due to Burst compilation.

### Burst Compiler

Burst compiler is very similar to Il2Cpp in the way it takes C# and converts it to Native code. This code is stored in a native library called `lib_burst_generated.dll`. The difference is burst uses a very limited subset of the C# language, which allows it to have simpler and faster native code.

Unfortunately currently we are not able to patch Burst compiled methods.

## Ghosts / Ghost Authoring

Ghosts part of the multiplayer client/server communication system. A ghost is a networked object that the server simulates. Read more on the Unity docs.

{% embed url="https://docs.unity3d.com/Packages/com.unity.netcode@1.0/manual/ghost-snapshots.html" %}

