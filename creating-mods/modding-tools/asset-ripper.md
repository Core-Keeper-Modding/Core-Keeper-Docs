---
description: >-
  A tool for extracting assets from Unity serialized files and converting them
  into the native Unity engine format.
---

# Asset Ripper

Asset Ripper will allow you to extract the base game's assets and load imitations of them in your modding SDK project.&#x20;

{% embed url="https://github.com/AssetRipper/AssetRipper" %}

After importing the assets you'll have to use the [Missing Script Recovery Tool](ng-tools-missing-script-recovery.md) to be able to view components and their settings.&#x20;

## Usage Directions

1. Download AssetRipper from its [releases page](https://github.com/AssetRipper/AssetRipper/releases)
2. Unzip the download and run `AssetRipper.GUI.Free.exe`
3. Follow the directions in the console window to access the GUI if it didn't already open in your browser automatically
4. Access `File` > `Settings` and ensure the following Options are checked, then click `Save`
   1. `Skip StreamingAssets Folder` - to avoid dumping mods
5. Use `File` > `Open Folder` to select your [game install directory folder](../../concepts/important-folder-paths.md#game-install-directory)
6. Go to `Export` > `Export All Files`&#x20;
7. Type or select (using the `Select Folder` button) a folder path to place the exported files at
8. Press the `Export Unity Project` button to start the export. The webpage displays no indication that anything is happening but the console window should be printing a bunch of stuff. Once the export is finished it will take you back to the Asset Ripper home page and the console log will end with "Export : Finished post-export"
9. Close the console window and browser tab

#### Export Audio Files

Audio Files are located in `StreamingAssets\aa`. If you want to export them you have 2 choice:

1. Ignoring step 4 in Usage Directions
2. Start at step 5 and select folder in your game install directory folder : `CoreKeeper_Data\StreamingAssets\aa`

### Navigating Exported Files

The `ExportedProject` folder contains all files we're interested in. Within this folder, you probably care about these subfolders:

* Textures can be found in `Assets\Texture2D`. Their respective sprites can be found in `Assets\Sprite`.
* Item and Entity prefabs can be found in `Assets\PrefabInstance`. These are usually not useful until they are [imported into the Mod SDK project and have their missing scripts fixed](../inspecting-base-game-content/importing-ripped-assets-to-your-editor.md).
* Sprite Assets can be found in `Assets\MonoBehaviour`, along with some other [Scriptable Objects](../../concepts/technologies-and-tools.md#scriptable-object)
* Audio files can be found in `Assets\Audio`
