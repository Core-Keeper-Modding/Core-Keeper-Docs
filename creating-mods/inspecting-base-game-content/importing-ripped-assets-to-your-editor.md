---
description: Bring base-game assets into your editor for quick reference.
---

# Importing Ripped Assets to your Editor

First, run Asset Ripper to export assets from the game.

{% content-ref url="../modding-tools/asset-ripper.md" %}
[asset-ripper.md](../modding-tools/asset-ripper.md)
{% endcontent-ref %}

Next, time to import them into your editor. Close the Unity editor first to keep it from wasting time hot refreshing as stuff is still being imported.

Go to the  `<export folder>\ExportedProject\Assets\` folder and copy only the following folders into your SDK project's assets folder. Copying anything not listed here risks bricking it.

* AnimationClip
* AnimatorController
* AnimatorOverrideController
* Font
* Material
* MonoBehaviour
* PrefabInstance
* Scenes
* Shader
* Sprite
* Texture2D

TODO what in the Resources directory is safe to bring in?

Reopen the Unity editor to allow it to rebuild its records, which will take a while.

## Fix Imported Prefabs

You will probably want to access the Prefabs you have imported. However, on prefabs, all scripts will be broken. Use the NG Tools Missing Script Recovery to restore them. Follow this guide to install it and use it:

{% content-ref url="../modding-tools/ng-tools-missing-script-recovery.md" %}
[ng-tools-missing-script-recovery.md](../modding-tools/ng-tools-missing-script-recovery.md)
{% endcontent-ref %}

You'll also have to use Unity Explorer to inspect the prefabs in-game to figure out what things are when Missing Script Recovery doesn't have enough context to work.

{% content-ref url="inspecting-assets-in-game.md" %}
[inspecting-assets-in-game.md](inspecting-assets-in-game.md)
{% endcontent-ref %}
