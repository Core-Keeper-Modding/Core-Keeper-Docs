---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# On Game Clients

The following approaches are available:

***

## Using the In-Game mod.io Integration

The in-game mod integration can be rather finicky, so **you may want to try another approach instead**. It has the following problems:

* Does not show you the list of mod dependencies (mods that must be installed for other mods to function)
* Sometimes does not automatically install mod dependencies for you
* Poor UX -  for example, in order to scroll the screen, you must click and drag the mouse, as the mouse wheel does nothing

If you still want to use this approach, simply launch the game and access the **Mods** screen from the main menu. To start using a mod, Subscribe to it. The game should automatically check for and install mod updates every launch.

It is highly suggested that you subscribe to each mod dependency individually to ensure it is downloaded correctly. You will have to view the mod on the mod.io website to see what they are.

For the best results, relaunch your game after installing or removing mods.

***

## Core Launcher

Core Launcher is a 3rd party tool that makes it easy to manage mods. Check out its page on GitHub for further directions.

Once you have installed it and set it up, create a Profile with the `+` button to start installing mods.

{% embed url="https://github.com/super-miner/Core-Launcher" %}

Core Launcher has a [dedicated discussion thread](https://discord.com/channels/851842678340845600/1173510418690490458) on the Core Keeper discord.

***

## Manual File Management&#x20;

If you'd rather manage mod files manually, you can download them from the mod's mod.io page and place them in the [mods folder](../../concepts/important-folder-paths.md#mod-files) yourself. Mods installed in this manner will never be automatically updated.

To do this:

1. Unsubscribe from all mods you are subscribed to on mod.io to prevent conflicts between the two approaches
2. Open your [game installation folder](../../concepts/important-folder-paths.md#game-install-directory)&#x20;
   *   On a default windows Steam installation, this is:&#x20;

       ```
       C:\Program Files (x86)\Steam\steamapps\common\Core Keeper\
       ```
   * If that path doesn't work for you, use the above link to find out where that is on your system
3. Go to the `CoreKeeper_Data\StreamingAssets\Mods` subfolder, creating any folders along the way if they do not already exist.
   *   On a default windows Steam installation, this is:&#x20;

       ```
       C:\Program Files (x86)\Steam\steamapps\common\Core Keeper\CoreKeeper_Data\StreamingAssets\Mods
       ```
4. Download the mods you want from the mod.io website using the Download File button
   * ![](../../.gitbook/assets/image.png)&#x20;
5. Unzip each of the mod zips you downloaded inside the folder so that each mod is in its own subfolder.
   * The name of each mod folder does not matter as long as it is unique, but you probably want it to include the name of the mod for later reference.
6. Ensure that each mod subfolder has a `ModManifest.json` file.
7. Good to go - launch the game and start playing!

***

## Alternative Entry Point Mods

Some mods do not use Core Keeper's modding system to interface with the game and cannot be installed using the means described above. In this case, it is up to the individual mod developer to explain how to install the mod.
