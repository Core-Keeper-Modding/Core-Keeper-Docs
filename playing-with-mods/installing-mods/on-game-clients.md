# On Game Clients

The following approaches are available:

***

## Using the In-Game mod.io Integration

The in-game mod integration can be rather finicky, so you may want to try another approach instead. It sometimes forgets to install dependencies. It also has poor UX - for example, in order to scroll the screen, you must click and drag the mouse, as the mouse wheel does nothing.

To use this approach, simply launch the game and access the Mods screen from the main menu. To start using a mod, subscribe to it. It is highly suggested that you subscribe to each mod dependency individually to ensure it is downloaded correctly. For the best results, relaunch your game after installing or removing mods.

***

## Core Launcher

Core Launcher is a 3rd party tool that makes it easy to manage mods. Check out its page on GitHub for further directions.

Core Launcher has a [dedicated discussion thread](https://discord.com/channels/851842678340845600/1173510418690490458) on the Core Keeper discord.

{% embed url="https://github.com/super-miner/Core-Launcher" %}

***

## Manual File Management&#x20;

If you'd rather manage mod files manually, you can download them from the mod's mod.io page and place them in the [mods folder](../../concepts/important-folder-paths.md#mod-files) yourself.

To do so open game installation folder and navigate to `<steam-game-folder>\Core Keeper\CoreKeeper_Data\StreamingAssets`. Create the folder `Mods` if it doesn't already exist and unzip mod zips into their own folders. The name of each mod folder does not matter as long as it is unique, but you probably want it to include the name of the mod for later reference.\
Ensure that each mod folder has a `ModManifest.json` file.

***

## Alternative Entry Point Mods

Some mods do not use Core Keeper's modding system to interface with the game and cannot be installed using the means described above. In this case, it is up to the individual mod developer to explain how to install the mod.
