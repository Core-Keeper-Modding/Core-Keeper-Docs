---
description: How to update your already installed Modding SDK project after a game update.
---

# Updating your Modding SDK

After updates to the Modding SDK repository (usually announced on the Discord) you will probably have to update your local copy for mods to work on the latest version.

Unfortunately, arbitrary things breaking between releases seems to be a very common occurrence in Core Keeper modding. Instead of trying to update your modding SDK, it is best to clone and set up a new one from scratch every time an update is released.

Read the Modding SDK Changelog to see what things Pugstorm is confident have changed between versions!

{% embed url="https://github.com/Pugstorm/CoreKeeperModSDK/blob/main/CHANGELOG.pdf" %}

Make sure to check the [Mod SDK Readme](https://github.com/Pugstorm/CoreKeeperModSDK?tab=readme-ov-file#requirements) to see if you need to install a new Unity version, and make sure to install Linux Mono build support on any new versions you install.

### Manual Mod SDK Update Guide

In the case you still want to manually update your mod SDK, follow these steps:

1. Download latest Mod SDK from [here](https://github.com/Pugstorm/CoreKeeperModSDK). Click on `Code`, then click `Download zip`
2. In your old Unity project delete following folders from the root of the project (It contains `Assets` folder): `Packages`, `Assets/Graphics`, `Assets/ModSDK`, `Assets/Resources`, `Assets/Unity`. If you have stored anything in there first move your files somewhere else.
3. Now proceed to copy all files from downloaded archive into your project folder (It contains `Assets` folder). Replace any existing files.
4. You're done. Try to open the project and see if it works. If you're getting errors you don't recognize, try cloning a fresh SDK instead.

