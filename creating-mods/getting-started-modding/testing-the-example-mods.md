# Testing the Example Mods

As described in [Max's guide on mod.io](https://mod.io/g/corekeeper/r/core-keeper-mod-sdk-introduction#heading-8), the modding SDK comes with some examples packaged in a zip file. Let's take a look at some of them.

## Extract the Examples

After your SDK project is set up, go to your file explorer and unzip the `/Assets/Examples.zip` file into the Assets folder such that you have a folder `/Assets/Examples` with a bunch of example subfolders.&#x20;

## Test the ItemExample Mod

In the Unity Editor, use a Project browser to navigate to the `/Assets/Examples/ItemExample` folder. Here you can see the files used by this example, which introduces a new weapon called "Sword1".

By inspecting `SpawnItemOnStart.cs` you can learn that the example is coded to create a dropped item instance of the custom item near spawn every time the game is loaded. This obviously is not what an end user would want, but it works well enough for our testing purposes.

To package the mod and try it out in-game, first open the Mod SDK tab. If you've lost it, you can open a new one via (Top bar) `PugMod` > `Open Mod SDK Window`.

Click the `Mod Settings` button to open the packaging UI, select `ItemExample` from the "Mod" dropdown, then click `Install Mod`. This will open a popup prompt and take at least a few seconds to execute. Once it's complete you'll see this popup:

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Launch the game and notice that the main menu's Mods button says you have 1 mod loaded (assuming you don't currently have any other mods loaded). If you were to go into this mods menu, the ItemExample mod would not show up because it has been installed outside of the mod.io ecosystem. This is to be expected for locally installed mods.

If you want to remove this mod, go to your [mod install directory](../../concepts/important-folder-paths.md#mod-files) and delete the `ItemExample` folder.

Load into a world and go near the Core - you'll find a Sword1 item on the ground.
