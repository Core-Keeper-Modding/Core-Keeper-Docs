# Getting started with modding

## Guide Deprecated

This guide was made for IL2CPP version of Core Keeper and no longer applies. Please refer to: [https://mod.io/g/corekeeper/r/core-keeper-mod-sdk-introduction](https://mod.io/g/corekeeper/r/core-keeper-mod-sdk-introduction)

## To start

To start modding this game follow these steps. This guide assumes you know C# language and familiar with it's tools.&#x20;

1. Install `Visual Studio` or `Jet Brains Rider` IDE. Both of these will work fine, however I personally would recommend Rider as its much better if you can get it.
2. Follow [BepInEx staring guide](https://docs.bepinex.dev/master/articles/dev\_guide/plugin\_tutorial/index.html) to setup your basic .NET project
3. Install DnSpy and [setup source viewing](view-source-code.md)
4. Make sure to use [CoreLib](https://github.com/Jrprogrammer/CoreLib) in your mod. It will make adding custom content easier
5. If you intent to make custom blocks, enemies, etc follow [Unity project setup guide](unity-setup.md)

Also below you can find the list of commonly used libraries and tools.

## Libraries

### BepInEx

BepInEx is a plugin framework for Unity and .NET framework games. We use BepInEx to load the mods into the game.

Be sure to select the IL2CPP code examples when you're creating your mod!

**Link:** [https://docs.bepinex.dev/master/articles/user\_guide/installation/index.html](https://docs.bepinex.dev/master/articles/user\_guide/installation/index.html)

**Download the latest IL2CPP build here**: [https://builds.bepinex.dev/projects/bepinex\_be](https://builds.bepinex.dev/projects/bepinex\_be)

### CoreLib

CoreLib is a modding library made specifically for Core Keeper. It provides a lot of features that make it easier creating your mods. This includes, but not limited to:

* Custom items, blocks, enemies, NPC, etc.
* Adding items using JSON
* Easier access to Rewired input system, localization
* Custom chat commands

To use it in your mods just add the [NuGet](https://www.nuget.org/packages/CoreKeeper.Modding.CoreLib/) to your project references

**Link:** [**https://github.com/Jrprogrammer/CoreLib**](https://github.com/Jrprogrammer/CoreLib)

### Harmony

Harmony is a library for patching, replacing and decorating existing classes and methods in the game. The patching is done in runtime, which means you don't have to change the existing code! We use harmony to run our code before or after game methods. This allows us to modify game behavior.

It is recommended to read through the Introduction, basics, patching and annotations chapters. Also please note that transpilers are not apllicable with Il2Cpp

**Link:** [https://harmony.pardeike.net/articles/intro.html](https://harmony.pardeike.net/articles/intro.html)

## Tools

### DnSpy

DnSpy is a tool that allows to read .NET assemblies code with ease. Unfortunately Core Keeper is made with the IL2CPP backend. This means we can't use DnSpy itself to view the source code. However it can be useful to view assemblies generated with Cpp2Il.

**Important!** If you look for a dnSpy tutorial, most will tell you to look for Assembly-CSharp.dll. This is **NOT** the case with Core Keeper and the relevant DLLs all begin with `Pug` (`Pug.Core`, `Pug.Other` and `PugWorldGen`)

**Link:** [https://github.com/dnSpy/dnSpy](https://github.com/dnSpy/dnSpy)

### Cpp2Il

Cpp2Il is a tool that attempts to reconstruct game assemblies, such that DnSpy would be able to read them. The tool is currently WIP and does not provide full and accurate output, however it is still useful.

**Link:** [https://github.com/SamboyCoding/Cpp2IL](https://github.com/SamboyCoding/Cpp2IL)

### Ghidra

Ghidra is a free and open source reverse engineering tool developed by the National Security Agency (NSA) of the United States. This tool allows us to read the `GameAssembly.dll` directly. This assembly contains compiled machine game code. To make it easier to find relevant code we can add Il2Cpp metadata. To do so we can use [Il2CppInspector](https://github.com/djkaty/Il2CppInspector) or [Il2CppDumper](https://github.com/Perfare/Il2CppDumper)

**Link:** [https://github.com/NationalSecurityAgency/ghidra/releases](https://github.com/NationalSecurityAgency/ghidra/releases)

### UnityExplorer

UnityExplorer is a BepInEx plugin that lets you inspect game objects and classes at the runtime. The main use for this tool is to figure out how to change something or check if your code worked correctly. It also has a C# REPL console which allows to execute code right in the game.

**Link:** [https://github.com/sinai-dev/UnityExplorer](https://github.com/sinai-dev/UnityExplorer)
