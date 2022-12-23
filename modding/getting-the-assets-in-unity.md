# How do I view the game's assets in unity?

This page provides a way to get a glimpse of the assets used in the game and even load them into Unity!

## Update Warning

With the release of the Desert update devs have changed Unity version to `2020.3.37` and also have refactored their assemblies. These changes will heavily break existing setups.

As such if you have setup Unity project before, I **HIGHLY** recommend to back it up, and start from scratch. After you setup the project from scratch you will need NG Tools Missing Script Recovery tool to fix scripts in your assets.

## Step 1: AssetRipper

Download the latest version of AssetRipper from their GitHub repository at [https://github.com/AssetRipper/AssetRipper](https://github.com/AssetRipper/AssetRipper). The name is pretty descriptive of what it does.

Extract the zipfile and open AssetRipper.exe.

Leave all the settings on default except for `Script Export Format` and `Script Content Level`, these should respectively be set to `Dll Export Without Renaming` and `Level 2`

Then drag and drop your game folder (The whole folder called `Core Keeper`) into AssetRipper.

Wait until AssetRipper is done loading the game content and then click on `Export > Export all files` in the left upper corner, and select a temporary folder.

You should now have a folder with all the assets of the game. It is recommended to copy this to your "projects" folder. The folder you need should have `Assets` folder in it. You can also rename this folder to your liking.

## Step 2: Preparing the folder for Unity

Go into the folder in the project root and open folder with the name `Packages`.

Create or open file with the name `manifest.json` in the `Packages` folder and paste this into the file:

```json
{
  "dependencies": {
    "com.unity.2d.sprite": "https://github.com/kremnev8/ModifiedCoreKeeperPackages.git?path=/com.unity.2d.sprite@1.0.0",
    "com.unity.assetbundlebrowser": "1.7.0",
    "com.unity.entities": "https://github.com/kremnev8/ModifiedCoreKeeperPackages.git?path=/com.unity.entities@0.51.1-preview.21",
    "com.unity.ide.rider": "2.0.7",
    "com.unity.ide.visualstudio": "2.0.16",
    "com.unity.ide.vscode": "1.2.5",
    "com.unity.netcode": "0.51.1-preview.21",
    "com.unity.performance.profile-analyzer": "1.1.1",
    "com.unity.physics": "https://github.com/kremnev8/ModifiedCoreKeeperPackages.git?path=/com.unity.physics@0.51.1-preview.21",
    "com.unity.platforms": "0.10.0-preview.10",
    "com.unity.postprocessing": "3.2.1",
    "com.unity.profiling.core": "1.0.2",
    "com.unity.rendering.hybrid": "0.51.1-preview.21",
    "com.unity.test-framework": "1.1.29",
    "com.unity.textmeshpro": "https://github.com/kremnev8/ModifiedCoreKeeperPackages.git?path=/com.unity.textmeshpro@3.0.6",
    "com.unity.scriptablebuildpipeline": "https://github.com/kremnev8/ModifiedCoreKeeperPackages.git?path=/com.unity.scriptablebuildpipeline@1.19.2",
    "com.unity.ugui": "1.0.0",
    "com.unity.modules.ai": "1.0.0",
    "com.unity.modules.androidjni": "1.0.0",
    "com.unity.modules.animation": "1.0.0",
    "com.unity.modules.assetbundle": "1.0.0",
    "com.unity.modules.audio": "1.0.0",
    "com.unity.modules.cloth": "1.0.0",
    "com.unity.modules.director": "1.0.0",
    "com.unity.modules.imageconversion": "1.0.0",
    "com.unity.modules.imgui": "1.0.0",
    "com.unity.modules.jsonserialize": "1.0.0",
    "com.unity.modules.particlesystem": "1.0.0",
    "com.unity.modules.physics": "1.0.0",
    "com.unity.modules.physics2d": "1.0.0",
    "com.unity.modules.screencapture": "1.0.0",
    "com.unity.modules.terrain": "1.0.0",
    "com.unity.modules.terrainphysics": "1.0.0",
    "com.unity.modules.tilemap": "1.0.0",
    "com.unity.modules.ui": "1.0.0",
    "com.unity.modules.uielements": "1.0.0",
    "com.unity.modules.umbra": "1.0.0",
    "com.unity.modules.unityanalytics": "1.0.0",
    "com.unity.modules.unitywebrequest": "1.0.0",
    "com.unity.modules.unitywebrequestassetbundle": "1.0.0",
    "com.unity.modules.unitywebrequestaudio": "1.0.0",
    "com.unity.modules.unitywebrequesttexture": "1.0.0",
    "com.unity.modules.unitywebrequestwww": "1.0.0",
    "com.unity.modules.vehicles": "1.0.0",
    "com.unity.modules.video": "1.0.0",
    "com.unity.modules.vr": "1.0.0",
    "com.unity.modules.wind": "1.0.0",
    "com.unity.modules.xr": "1.0.0"
  }
}
```

Save `manifest.json` and go back into project root. Make sure that you have git installed and it's executable is in your PATH environment variable. After installing git make sure to close Unity and Unity hub completely!

Move all the files in the `Assets/Plugins` folder to somewhere safe and make sure the folder is empty.

Note: `Plugins` could be called differently. Devs of Asset Ripper change it's name all the time. If you can't see it, look for a folder in `Assets` folder with `.dll` files in it.

## Step 3: Installing The right Unity version.

Install Unity version `2020.3.37f1` from the Unity Download Archive: [https://unity3d.com/get-unity/download/archive](https://unity3d.com/get-unity/download/archive).

Go through the standard Unity installation and wait until it's done.

## Step 4: Opening the project.

Open the Unity hub and select the folder you created when exporting the AssetRipper files.

Open the project with Unity version `2020.3.37f1` and wait for it to load. This can take a while.

## Step 5: Adding Script Assemblies

Find the temp folder in where you placed files from Plugins folder earlier. Copy paste all contents from the script **EXCEPT** the following:

* All Unity assemblies which start with `Unity.` (errors will occur due to duplicate assemblies if these are pasted in)
* `Assembly-CSharp`

back into `Assets/MonoScript`.&#x20;

**Note:** keep assemblies with `Sentry` in the name, even if they have `Unity` in the name

Make sure that you are doing this while Unity is **RUNNING**. Otherwise it will crash!

## Step 6: Restart Unity

Restart Unity to fully get the project assembled.

## Step 7: Profit

You should now be able to see the assets in the Unity editor.

Enjoy and make some cool stuff.&#x20;

## Utilities and helpful tools

Due to switching Unity.Physics assembly, there will be missing script references. [This tool](https://assetstore.unity.com/packages/tools/utilities/ng-missing-script-recovery-102272) will help with the missing script references.

When using CoreLib library you can add an Editor Kit to your project. This kit will add custom component dummies and also useful editor extensions.
