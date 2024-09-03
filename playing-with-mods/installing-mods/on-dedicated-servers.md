# On Dedicated Servers

The following approaches are available:

***

## Manual File Management

Open game installation folder and navigate to `<steam-game-folder>\Core Keeper\CoreKeeper_Data\StreamingAssets`.&#x20;

Create the folder `Mods` if it doesn't already exist and unzip mod zips into their own folders. The name of each mod folder does not matter as long as it is unique, but you probably want it to include the name of the mod for later reference. Ensure that each mod folder has a `ModManifest.json` file.

Some mods only need to be installed client side or server side to function properly. The Mod SDK allows developers to specify if a mod is required on both sides, but mod.io does not display it to users anywhere, so it's up to the mod developer to tell you this somehow in the description page.

If the mod developer doesn't specify, it's best to **assume the mod is required on all sides**.

***
