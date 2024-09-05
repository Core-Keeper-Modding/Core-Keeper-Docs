# Create a mod.io Page

You should have already created a mod.io account as part of [setting up the Modding SDK](../getting-started-modding/setting-up-the-modding-sdk.md). Now it's time to create a page for your mod. This is what end users will see when they are looking at your mod for the first time, so make it professional if you want to leave a good impression.

## Read the mod.io Guidelines

Make sure that your mod complies with the guidelines described here:

{% embed url="https://mod.io/g/corekeeper/r/user-guidelines" %}

## Write a Description

Here is the _bare minimum_ _information_ you should describe in your mod page description:

* Directions on how to access and configure your mod's features.
  * What crafting bench are the items made in?
  * Where do you configure keybinds, and what are the defaults?&#x20;
* How users should report bugs
  * A GitHub issue tracker? Contact you on discord? The mod.io comments section?
* If the mod is required by all users in multiplayer, just the client, or just the server

Here is other stuff to consider including:

* Screenshots of the mod in action. People like pictures!
* Known bugs (or a link to a bug tracker)
* "Special Thanks" to list other people that helped your mod come to be

## Apply Tags

Use the "Game Version" tags to indicate what versions your mod supports. If a user doesn't see the latest game version tag on your mod, they might think it's broken, and the game may report the mod as out of date to the user.

Use the "Type" tags as categories for summarizing what kinds of content your mod adds.

Use tags "Application Type" to help users understand where the mod needs to be installed. Mark the mod as "Client" if the mod is intended to be installed on the client, mark the mod as "Server" if the mod is intended to be installed on the server. Tick both if both sides must have the mod.

"Access Type" tag sets mod loading behavior. If mod has "Asset" tag, scripts WONT be loaded at all. If the mod has tag "Script" (Or if it hasn't set any tags in "Access Type". This is legacy behavior), its scripts will be loaded. Use the "Script (Elevated Access)" tag if your mod needs [elevated access](../../concepts/elevated-access.md).

## Dependencies

List any other mods or libraries that your mod depends on. The Mod SDK upload utility might have automatically filled this out for you.

