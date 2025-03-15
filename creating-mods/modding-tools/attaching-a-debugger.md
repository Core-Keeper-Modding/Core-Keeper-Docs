# Attaching a Debugger

The tutorial is referenced from [https://github.com/dnSpyEx/dnSpy/wiki/Debugging-Unity-Games](https://github.com/dnSpyEx/dnSpy/wiki/Debugging-Unity-Games)

1. Download the correct version of UnityEditor from Unity Hub (You can right-click CoreKeeper.exe -> Properties to get the unity editor version number. Usually it is the same as the required version of the ModSDK).
2. Locate the unityPlayer folder (Example:  C:\Program Files\Unity\Hub\Editor\2022.3.50f1\Editor\Data\PlaybackEngines\windowsstandalonesupport\Variations\win64\_player\_development\_mono).
3. Backup Game Files
4. Copy and overrite UnityPlayer.dll, WinPixEventRuntime.dll, WindowsPlayer.exe to game folder (Example: D:\Steam\steamapps\common\Core Keeper) and rename WindowsPlayer.exe to CoreKeeper.exe (overrite).
5. Copy and overrite Managed folder (Example: C:\Program Files\Unity\Hub\Editor\2022.3.50f1\Editor\Data\PlaybackEngines\windowsstandalonesupport\Variations\win64\_player\_development\_mono\Data\Managed) to \[GameFolder]\CoreKeeper\_Data (Example: D:\Steam\steamapps\common\Core Keeper\CoreKeeper\_Data)
6. Launch game by CoreKeeper.exe. (Not steam, Because I'm not sure if this will trigger steam's integrity checking mechanism.)
7. Wait for the game to finish loading, then you can attach any debugger (Dnspy \[In this way there is no need to patch Mono, because we have already converted the game from release to debug, and this is the solution without the patched mono from 2022.x version.], JetBrains Rider, Visual Studio), you can't use start and attach, because the first process that starts will automatically crash and close, and the second process is what we need for the game itself.
