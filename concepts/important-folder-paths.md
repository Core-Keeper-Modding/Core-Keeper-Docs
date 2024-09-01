# Important Folder Paths

## Game Install Directory

### Steam

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

### Xbox Desktop Application

If you know where to find these files, update the docs to add this info!

## Log Files

Windows Client:  `%userprofile%\appdata\locallow\Pugstorm\Core Keeper`

Linux Client: `TODO`

Linux Server: Placed in same folder as the server executable. No past logs are kept.

## Save Files

### Character Save Files

Windows: `%USERPROFILE%\AppData\LocalLow\Pugstorm\Core Keeper\Steam\<user-id>\saves`

Linux Client: `$HOME/.config/unity3d/Pugstorm/Core Keeper/Steam/<user-id>/saves`

Linux Server: Not applicable

### World Save Files

Windows: `%USERPROFILE%\AppData\LocalLow\Pugstorm\Core Keeper\Steam\<user-id>\worlds`

Linux Client: `$HOME/.config/unity3d/Pugstorm/Core Keeper/Steam/<user-id>/worlds`

Linux Server: `/Save/worlds` subfolder of the server install directory.

## Mod Files

### Desktop Mods (Auto-Downloaded via mod.io)

Mods automatically downloaded by mod.io can be found at `C:\Users\Public\mod.io\5289`. The folder contains:

\-`state.json` , a file that encodes subscribed mods and their state.

\- `mods/`, a folder which contains all downloaded mods. The folder names are mod.io IDs and are not human readable unless you lookup the IDs using the API. You can edit or delete files in this folder to remove or unsubscribe from mods.

### Desktop Mods (Manually Added)

`CoreKeeper_Data\StreamingAssets\Mods` subfolder of your [game install directory](important-folder-paths.md#game-install-directory). This is where mod developers can find the mods packaged by the Unity editor during mod development.

### Dedicated Server Mods

Server mods are placed in the `CoreKeeperServer_Data\StreamingAssets\Mods` subfolder of the server install directory.

## Mod Configuration Files

Windows: `%USERPROFILE%\AppData\LocalLow\Pugstorm\Core Keeper\Steam\<user-id>\mods`

Linux Client: `TODO`

Linux Server: `/Save/mods`subfolder of the server install directory.

