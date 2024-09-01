---
description: How to install mods!
---

# Installing Mods

## On Game Clients

### In-Game Mod Integration

The in-game mod integration can be rather finicky, so you may want to try another approach instead. It can very easily forget which mods you have installed or forget to install dependencies. It also has pretty terrible UX - for example, in order to scroll the screen, you must click and drag the mouse, as the mouse wheel does nothing.

To use this approach, simply launch the game and access the Mods screen from the main menu. To start using a mod, subscribe to it. It is highly suggested that you subscribe to each mod dependency individually to ensure it is downloaded correctly.

### Core Launcher

Core Launcher is a 3rd party tool that makes it easy to manage mods.

Check out its page on GitHub for further directions.

{% embed url="https://github.com/super-miner/Core-Launcher" %}

Core Launcher has a [dedicated discussion thread](https://discord.com/channels/851842678340845600/1173510418690490458) on the Core Keeper discord.

### Manual File Management&#x20;

If you'd rather manage mod files manually, you can download them from the mod's mod.io page and place them in the [mods folder](../concepts/important-folder-paths.md#mod-files) yourself.\
\
To do so open game installation folder and navigate to `<steam-game-folder>\Core Keeper\CoreKeeper_Data\StreamingAssets`. Create the folder `Mods` if it doesn't already exist and unzip mod zips into their own folders. The name of each mod folder does not matter as long as it is unique, but you probably want it to include the name of the mod for later reference.\
Ensure that each mod folder has a `ModManifest.json` file.

### Alternative Entry Point Mods

Some mods do not use Core Keeper's modding system to interface with the game and cannot be installed using the means described above. In this case, it is up to the individual mod developer to explain how to install the mod.

## On Dedicated Servers

Dedicated servers only support manual installation method. Open the[ mods folder ](../concepts/important-folder-paths.md#dedicated-server-mods)and follow the same procedure as for the game.

Some mods only need to be installed client side or server side to function properly. The Mod SDK allows developers to specify if a mod is required on both sides, but mod.io does not display it to users anywhere, so it's up to the mod developer to tell you this somehow in the description page.

If the mod developer doesn't specify, it's best to **assume the mod is required on all sides**.
