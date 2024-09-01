---
description: >-
  CoreLib is a set of libraries developed by Limoka/Kremnev to make modding Core
  Keeper easier.
---

# CoreLib

CoreLib can be found on mod.io here:

{% embed url="https://mod.io/g/corekeeper/m/core-lib" %}

Source code for CoreLib (and all submodules) is public on GitHub:

{% embed url="https://github.com/CoreKeeperMods/CoreLib" %}

To install CoreLib in your modding SDK, follow the directions in its [readme](https://github.com/CoreKeeperMods/CoreLib/blob/main/README.md). You can find out the latest version number to pin by looking at the [most recent tag name](https://github.com/CoreKeeperMods/CoreLib/tags).



When creating a mod that depends on CoreLib, make sure to list every module dependency and the root CoreLib mod as a direct dependency of your mod. The game's mod.io integration sucks at downloading dependencies correctly, let alone transitive dependencies, and doing this helps ensure it correctly downloads everything.
