---
description: >-
  Use additional tools to inspect properties and values while the game is
  running.
---

# Inspecting Assets In-Game

{% content-ref url="../modding-tools/unity-explorer.md" %}
[unity-explorer.md](../modding-tools/unity-explorer.md)
{% endcontent-ref %}

## Example Cases

### Fixing an imported MinecartEntity prefab by looking at the real one in game

1. Install [Unity Explorer](../modding-tools/unity-explorer.md) and relaunch the game
2. Open the "Object Explorer" window from the newly added top bar
   1.

       <figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
3. Switch to "Object Search" mode and type `MinecartEntity` into the "Name contains:" search box, then press Search
   1.

       <figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
4. Find the entry `"MinecartEntity" (UnityEngine.GameObject)` and double click it&#x20;
   1.

       <figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
5. In the "Components" column you can see a list of script components on the prefab. The default sorting order should be exactly the same as the sorting order of the scripts in the Unity editor.
   1.

       <figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
6. Use [NG Tools Missing Script Recovery](../modding-tools/ng-tools-missing-script-recovery.md) to fix as many Perfect Matches as you can, then use the entries in the Components column to specify what the rest of the scripts are.
