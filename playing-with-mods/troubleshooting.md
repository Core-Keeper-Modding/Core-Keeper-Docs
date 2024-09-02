---
description: If you're encountering problems using mods, this page might have the solution.
---

# Troubleshooting

{% hint style="info" %}
TIP: You can use your browser's Find feature (usually `Ctrl`+`F`) to search this page for error messages you've encountered.&#x20;
{% endhint %}

## Problems and Error Messages

{% hint style="info" %}
Each entry in this section has a list of clickable links to directions on trying that fix approach.
{% endhint %}

### I installed mods, but they don't seem to be doing anything

* [#read-the-mods-documentation](troubleshooting.md#read-the-mods-documentation "mention") to find out how to access its features.
* [Did you accidentally launch in "No Mods" mode?](uninstalling-mods.md#launch-the-game-in-no-mods-mode-then-unsubscribe-from-mods)
* Check the tags on the mod.io page - is the mod not updated for this game version yet?
* [#install-the-mod-reporter-mod-to-check-for-loading-errors](troubleshooting.md#install-the-mod-reporter-mod-to-check-for-loading-errors "mention")&#x20;
* [#check-your-log-files-for-error-messages](troubleshooting.md#check-your-log-files-for-error-messages "mention")  - sometimes mods can error in ways that don't get caught by Mod Reporter
* [#ask-for-help-on-the-discord](troubleshooting.md#ask-for-help-on-the-discord "mention")
* [reporting-bugs.md](reporting-bugs.md "mention")

### "Mods" menu on title screen does not load (`Failed to Fetch`)

* [#launch-the-game-in-no-mods-mode-then-unsubscribe-from-mods](uninstalling-mods.md#launch-the-game-in-no-mods-mode-then-unsubscribe-from-mods "mention")  - remove mods until the problem stops to track down what mod was causing the problem.
* [#ask-for-help-on-the-discord](troubleshooting.md#ask-for-help-on-the-discord "mention")

### Can't join my friend's multiplayer game

* Make sure that both players have exactly the same mods installed, removing any possibility of a mismatch.
* [#check-your-log-files-for-error-messages](troubleshooting.md#check-your-log-files-for-error-messages "mention")
* [#ask-for-help-on-the-discord](troubleshooting.md#ask-for-help-on-the-discord "mention")

### Help, my game is crashing

This most common cause of this is installing broken or outdated mods.

* [#install-the-mod-reporter-mod-to-check-for-loading-errors](troubleshooting.md#install-the-mod-reporter-mod-to-check-for-loading-errors "mention")
* [uninstalling-mods.md](uninstalling-mods.md "mention")  - remove mods until the problem stops to track down what mod was causing the problem.
* [#ask-for-help-on-the-discord](troubleshooting.md#ask-for-help-on-the-discord "mention")
* Once you find out what mod in specific is the cause - [reporting-bugs.md](reporting-bugs.md "mention")

### `Failed to create mod on mod.io: Api failed to complete the request`

* Try [uploading the mod manually](../creating-mods/releasing-mods/mod-files-upload.md)

### `Command give does not exist!`

You did not properly install the chat commands mod, or something is preventing it from loading.

* [#install-the-mod-reporter-mod-to-check-for-loading-errors](troubleshooting.md#install-the-mod-reporter-mod-to-check-for-loading-errors "mention")
* [#manually-subscribe-to-all-of-a-mods-dependencies](troubleshooting.md#manually-subscribe-to-all-of-a-mods-dependencies "mention")
* Try [uninstalling the mod](uninstalling-mods.md) then [installing it (and its dependencies) via another method](installing-mods.md).

***

## Fix Approaches

_This section contains troubleshooting approaches for the above problems to link to._

### Install the Mod Reporter mod to check for loading errors

The **Mod Reporter** mod provides a GUI on the main menu to view the current state of your installed mods and see any issues easily.

{% embed url="https://mod.io/g/corekeeper/m/mod-reporter" %}

### Check your log files for error messages

Take a look at your [game log files](../concepts/important-folder-paths.md#log-files) to see if any mods are reporting errors.

### Read the Mod's Documentation

Check for directions on how to use the mod, known issues, etc. on the mod's page on mod.io.

### Manually subscribe to all of a mod's dependencies

The game's mod.io integration often fails to download mod dependencies. Visit the mod's page on the [mod.io website](https://mod.io/g/corekeeper/) to see what they are and manually subscribe to each of them.

### Ask for Help on the Discord

Join the [Core Keeper discord](https://discord.com/invite/corekeeper) and ask for help in the #modding-help channel. Make sure to mention:

* What mods you are using.
* What you expected to happen,and what actually happened.
* If you're playing in singleplayer, multiplayer, or a dedicated server, and if you're the host or the client.
* Your [log files](../concepts/important-folder-paths.md#log-files)! It will be the first thing people ask for if you don't provide it.

Remember to _communicate what you fixes have already tried_. People are a lot more willing to help if you make it clear you've already put in some effort!
