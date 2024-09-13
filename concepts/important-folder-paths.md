# Important Folder Paths

## Game Install Directory

### Steam

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

### Xbox Desktop Application

If you know where to find the Xbox desktop install files, [update the docs](../how-to-contribute.md) to add this info!

## Log Files

{% tabs %}
{% tab title="Windows Client" %}
`%userprofile%\appdata\locallow\Pugstorm\Core Keeper`
{% endtab %}

{% tab title="Linux Client" %}
TODO - do you know where it is? [Add it](../how-to-contribute.md)!
{% endtab %}

{% tab title="Dedicated Server" %}
Placed in same folder as the server executable. No past logs are kept.
{% endtab %}
{% endtabs %}

## Save Files

### Character Save Files

{% tabs %}
{% tab title="Windows Client" %}
`%USERPROFILE%\AppData\LocalLow\Pugstorm\Core Keeper\Steam\<user-id>\saves`
{% endtab %}

{% tab title="Linux Client" %}
`$HOME/.config/unity3d/Pugstorm/Core Keeper/Steam/<user-id>/saves`
{% endtab %}

{% tab title="Dedicated Server" %}
Not applicable - characters exist client side.
{% endtab %}
{% endtabs %}

### World Save Files

{% tabs %}
{% tab title="Windows Client" %}
`%USERPROFILE%\AppData\LocalLow\Pugstorm\Core Keeper\Steam\<user-id>\worlds`
{% endtab %}

{% tab title="Linux Client" %}
`$HOME/.config/unity3d/Pugstorm/Core Keeper/Steam/<user-id>/worlds`
{% endtab %}

{% tab title="Dedicated Server" %}
`/Save/worlds` subfolder of the server install directory.
{% endtab %}
{% endtabs %}

## Mod Files

There are 2 locations where mod files are stored:

### Auto-Downloaded via mod.io

This is where the game's mod.io integration downloads the mods you are subscribed to.

{% tabs %}
{% tab title="Windows Client" %}
`C:\Users\Public\mod.io\5289`
{% endtab %}

{% tab title="Linux Client" %}
TODO - do you know where it is? [Add it](../how-to-contribute.md)!
{% endtab %}

{% tab title="Dedicated Server" %}
Not applicable - servers can't use the mod.io integration. See the [#manually-added-mods](important-folder-paths.md#manually-added-mods "mention") section.
{% endtab %}
{% endtabs %}

The folder contains:

* `state.json` , a file that encodes subscribed mods and their state.
* `mods/`, a folder which contains all downloaded mods. The folder names are mod.io IDs and are not human readable unless you lookup the IDs using the API. You can edit or delete files in this folder to remove or unsubscribe from mods.

### Manually Added Mods

If you want to downloads mods manually, this is where you should put them. This is also where mod developers can find the mods packaged by the Unity editor during mod development.

{% tabs %}
{% tab title="Windows Client" %}
`CoreKeeper_Data\StreamingAssets\Mods` subfolder of your [game install directory](important-folder-paths.md#game-install-directory).

For example:

```
C:\Program Files (x86)\Steam\steamapps\common\Core Keeper\CoreKeeper_Data\StreamingAssets\Mods
```
{% endtab %}

{% tab title="Linux Client" %}
`CoreKeeper_Data\StreamingAssets\Mods` subfolder of your [game install directory](important-folder-paths.md#game-install-directory).
{% endtab %}

{% tab title="Dedicated Server" %}
`CoreKeeperServer_Data\StreamingAssets\Mods` subfolder of the server install directory.
{% endtab %}
{% endtabs %}

## Mod Configuration Files

{% tabs %}
{% tab title="Windows Client" %}
`%USERPROFILE%\AppData\LocalLow\Pugstorm\Core Keeper\Steam\<user-id>\mods`
{% endtab %}

{% tab title="Linux Client" %}
TODO - do you know where it is? [Add it](../how-to-contribute.md)!
{% endtab %}

{% tab title="Dedicated Server" %}
`/Save/mods`subfolder of the server install directory.
{% endtab %}
{% endtabs %}

