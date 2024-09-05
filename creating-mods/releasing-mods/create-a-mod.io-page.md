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
* Link to mod source repository (ex. GitHub)
* "Special Thanks" to list other people that helped your mod come to be

## Apply Tags

Tags help categorize your mod and assist users with finding it. Some tags also have special functionality.

### Game Version

Use the "Game Version" tags to indicate what versions your mod supports. If a user doesn't see the latest game version tag on your mod, they might think it's broken, and the game may report the mod as out of date to the user.

### Type

Use the "Type" tags as categories for summarizing what kinds of content your mod adds and changes it makes. You can select as many or as few as you want.

### Application Type

Use tags "Application Type" to help users understand where the mod needs to be installed in [multiplayer](../../playing-with-mods/installing-mods/for-multiplayer.md).

| Tag Combination             | Purpose                                                                                     |
| --------------------------- | ------------------------------------------------------------------------------------------- |
| Client                      | Mod must be installed on game clients to function correctly.                                |
| Server                      | Mod must be installed on host-and-play servers and dedicated servers to function correctly. |
| Client, Server              | Mod must be installed for on all sides to function correctly.                               |
| (No Application Type tags)  | Don't do this, it makes it unclear where the mod should be installed.                       |

### Access Type

"Access Type" tags control mod loading behavior. Only one should be selected at a time.

| Tag Combination          | Purpose                                                                                            |
| ------------------------ | -------------------------------------------------------------------------------------------------- |
| (No Access Type tags)    | Legacy compatibility behavior - does the same thing as the Script tag. Don't do this.              |
| Asset                    | No mod scripts will be loaded.                                                                     |
| Script                   | Mod scripts will be loaded. Most mods involve some scripts; this is the most commonly used option. |
| Script (Elevated Access) | Loads mod scripts in [Elevated Access](../../concepts/elevated-access.md) mode.                    |

## Dependencies

List any other mods or libraries that your mod depends on. The Mod SDK upload utility might have automatically filled this out for you.

