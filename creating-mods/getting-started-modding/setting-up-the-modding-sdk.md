# Setting Up the Modding SDK

Max at Pugstorm maintains a guide for accessing and installing the modding SDK on mod.io guides.

Follow Max's guide up until you reach the "Creating new objects" header. You can keep reading from there if you'd like, but it may not make sense without further context. This site will walk through some more specific examples in the next few pages.&#x20;

{% embed url="https://mod.io/g/corekeeper/r/core-keeper-mod-sdk-introduction" %}

As Max is the only person with edit permissions, the mod.io guide can easily fall out of date. If something needs to be updated, discuss it in the #mod-creators channel on the [official Core Keeper Discord](https://discord.com/invite/corekeeper).

## Additional Steps

There are a few extra steps you need to take that Max's guide doesn't mention.

### Disable Assembly Updater

In the Unity Hub, add the `-disable-assembly-updater` command line argument to your SDK project. If you don't do this, the `Pug.Other.dll` and `Pug.ECS.Components.dll` will not load correctly, meaning you will be missing some important script components.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
