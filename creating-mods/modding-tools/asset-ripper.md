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

### Navigating Exported Files

`ExportedProject` folder contains all files we're interested in. Next section references paths relative to it.

* Textures can be found in `Assets\Texture2D`. Their respective sprites can be found in `Assets\Sprite`
* Item and Entity prefabs can be found in `Assets\PrefabInstance`. These very likely will have missing scripts when you put them in Mod SDK. To fix these, use [script recovery tool](ng-tools-missing-script-recovery.md). If a script has no fields use [Unity Explorer](unity-explorer.md) to inspect the prefab ingame
* Sprite Assets can be found in `Assets\MonoBehaviour`, along with some other [Scriptable Objects](../../concepts/technologies-and-tools.md#scriptable-object)
* TODO where are sounds?
