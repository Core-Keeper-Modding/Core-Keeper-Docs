# Tools used in the game

This game is using a few tools that are important to understand while modding. Specifically these are Il2Cpp, DOTS, ECS, Jobs system and Burst

## Il2Cpp

Il2Cpp is a build backed for Unity Engine. It performs a conversion of the game code (Written in C#) to cpp. Then using special library called libil2cpp it compiles the game code to native binary.&#x20;

When Unity compiles for Il2Cpp it also performs heavy stripping and anything that devs did not use can and will be stripped. This is especially true for generic types and methods which use structs.

## DOTS

Data-Oriented Technology Stack (DOTS) is a new feature of Unity, which is currently is in pre release. It uses completely different way of thinking about game state than usual Game Object based approach.&#x20;

With DOTS also come ECS, Job Systems and Burst

### ECS

Entity Component System (ECS) is the main package for DOTS. It provides the core feature of DOTS: Entities, Components and Systems

Entities are containers for many Components. The class itself is just a identifier into the ECS state.

Components are structs, which hold component data. However they don't hold any behavior.

Systems hold the actual behavior. They can perform operations of group of components in bulk, utilizing Job Systems and Burst to do so in multi-threaded way

#### Authoring

When making the game and it's prefabs, devs are using Hybrid system, which allows to **author** the content using typical game objects and MonoBehavior based components.

After the game is loaded each Authoring component performs conversion from game object world to ECS world and ECS components.

### Job Systems

Jobs are the way devs write system behavior which allows to easy multi-threading.&#x20;

Unfortunately for us, we can't create custom Jobs. And patching such jobs also currently poses an issue due to Burst compilation.

### Burst Compiler

Burst compiler is very similar to Il2Cpp in the way it takes C# and converts it to Native code. This code is stored in a native library called `lib_burst_generated.dll`. The difference is burst uses a very limited subset of the C# language, which allows it to have simpler and faster native code.

Unfortunately currently we are not able to patch Burst compiled methods.
