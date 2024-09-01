---
description: >-
  Use this page to temper your expectations about what Core Keeper modding can
  achieve.
---

# Modding Limitations

## Unexpectedly Complex Things to Mod

_Things in this section are not necessarily hard to mod, but are not as easy as people usually expect them to be._

### "A copy of \<base-game content>, but with \<this thing tweaked>"

Because of how the modding API requires modders to define and register content, creating a copy of existing base-game content can be unexpectedly difficult if not impossible.

***

## Hard Things to Mod

_Things in this section are possible to mod, but are harder than they seem._

### Texture Packs

Adding generic texture packs can be rather painful. The issue stems from the fact there is no single place you could replace the textures in. You will have to write specific code for each kind of object.\
\
Very specific texture altering mods however are relatively easy to create.

***

## Prohibitively Difficult to Mod

_Things in this section are technically possible to mod, but a massive pain._

### World Generation

World generation in 1.0 is implemented with GPU shaders. Altering said shader atm is not possible. However custom world generation could theoretically be done after the fact.\


If you are interested in this, here's a tip from game developer Fewes:

> What you can likely do right now is use the new API functions `PugWorld.RequestArea` and `PugWorld.RequestPoints`, along with their callbacks `PugWorld.onAreaRequestComplete` and `PugWorld.onPointsRequestComplete` to sample the world generation shader and get data back which you can use however you want.

### Bursted Code

A number of sections of the code are compiled with Burst for performance reasons, making modifying them a massive pain. More info [here](../concepts/technologies-and-tools.md#burst-compiler).

***

## Basically Impossible to Mod

_Limitations in the modding API make it basically impossible to modify these things._ Have you found a way to modify them despite this? [Contribute to the docs](../how-to-contribute.md) and explain how!

### TODO - Put something here

There are definitely things that are impossible to mod but no one has written them down yet.
