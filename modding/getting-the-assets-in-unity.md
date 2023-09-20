# How to setup your Unity project

## Guide Deprecated

This guide was made for IL2CPP version of Core Keeper and no longer applies. Please refer to: [https://mod.io/g/corekeeper/r/core-keeper-mod-sdk-introduction](https://mod.io/g/corekeeper/r/core-keeper-mod-sdk-introduction)

This guide provides step by step guide on how to setup your Unity project to create custom assets or view game assets

## Quality of Love Update Warning

With the release of Quality of Love update devs have changed Unity version to `2021.3.14` and switched to Universal Rendering Pipeline. Both of these changes complicate Unity project setup.

## Desert Update Warning

With the release of the Desert update devs have changed Unity version to `2020.3.37` and also have refactored their assemblies. These changes will heavily break existing setups.

## Backup your project

If you have setup Unity project before and there was Unity version update, I **HIGHLY** recommend to back it up, and start from scratch. After you setup the project from scratch you will need NG Tools Missing Script Recovery tool to fix scripts in your assets.

## ThunderKit based Guide

With release of the mono build of the game it is now possible to use ThunderKit to setup our Unity project.

## Step 1: Install Unity

Install Unity Hub from [https://unity.com/download](https://unity.com/download)

Install Unity version `2021.3.14f1` from the Unity Download Archive: [https://unity3d.com/get-unity/download/archive](https://unity3d.com/get-unity/download/archive) using Unity Hub

Go through the standard Unity installation and wait until it's done.

Make sure that you have git installed and it's executable is in your PATH environment variable. After installing git make sure to close Unity and Unity hub completely!

## Step 2: Install Mono version of Core Keeper

Install [Core Keeper mono version](how-to-install-core-keeper-mono-version.md)

## Step 3: Setup the project

### Create a new project

Create a new project from 2D Core template using Unity Hub. Wait until project is created and imported.

### Install ThunderKit

Now in the menu bar click on `Window/Package Manager`. A window will appear. In the top left corner click install button, select `add package from git URL` and paste in this link: `https://github.com/kremnev8/ThunderKit.git#master`

Wait for ThunderKit to be installed

### Install Core Keeper Import Extensions

In the menu bar go to `Tools/ThunderKit/Packages`. Now install `Core Keeper Import Extensions` package.&#x20;

Once it is installed in the ThunderKit settings tab `Import Configuration`. You should see a bunch of new importers.

### Import game assemblies

In ThunderKit settings tab `ThunderKit Settings`. Click on the `Browse` button. Select the executable of your Mono Core Keeper. Now click on the `Import` button

This step might take a while to complete. Once it's done, you will be asked to restart Unity, click `Restart Project`

## Optional steps

At this point your project is functional. You can create custom assets and export them. Next steps are optional.

## Add game assets to your project

### Install Asset Ripper

Download the latest version of AssetRipper from their GitHub repository at [https://github.com/AssetRipper/AssetRipper](https://github.com/AssetRipper/AssetRipper). The name is pretty descriptive of what it does.

Extract the zipfile and open AssetRipper.exe.

### Extract Assets

Leave all the settings on default except for `Script Export Format` and `Script Content Level`, these should respectively be set to `Dll Export Without Renaming` and `Level 2`

Then drag and drop your game folder (The whole folder called `Core Keeper`) into AssetRipper.

Wait until AssetRipper is done loading the game content and then click on `Export > Export all files` in the left upper corner, and select a temporary folder.

You should now have a folder with all the assets of the game.

### Move Assets

In the extracted folder look for `Assets` folder. From it you want every folder APART from `Plugins`.&#x20;

In your project `Assets` folder create a folder to house these assets, for example `Core Keeper` and move all files from exported `Assets` there.

Now Unity will start to import these. This will take a while to complete.

## Other Utilities

There might be missing script references. [This tool](https://assetstore.unity.com/packages/tools/utilities/ng-missing-script-recovery-102272) will help with the missing script references.

## Old (Legacy) Guide

Previous version of this guide can be found [here](../archive/old-unity-guide.md)
