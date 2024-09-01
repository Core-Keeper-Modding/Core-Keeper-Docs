---
description: >-
  This page describes how to create various item archetypes. For example:
  ingredients, tools and weapons, etc.
---

# Items

Item are the simplest form of content you can add to the game. These range from things like wood to sword and armor.

## Basic Item

To create an item, first create a new Prefab (Right click in the project tab, `Create` -> `Prefab`).

Open the prefab and add following components: `ObjectAuthoring`, `InventoryItemAuthoring`.

### ObjectAuthoring

This component defines what this object is.

First field you must fill out is `Object Name`. Following the naming pattern: `ModName:ItemName`. Learn more about Object Names [here](../../common-concepts/unique-names-and-ids.md).

Next field you must set is the Object Type. This field defines the kind of item this is. For this example set it to `Non Usable`.&#x20;

You may fill other fields on your own discretion.

### InventoryItemAuthoring

This component defines information about the item for display in the inventory.

You must fill out fields `Icon` and `Small Icon`. These are the icons the player will see ingame. Both need to be `16x16` px.

Here you can also define item's crafting recipe, sell and buy values, and whether it can be stacked. Crafting recipes will be covered in another guide.

### Item Localization

To set item's localized name create folder named Localization in your mod root folder. Now create a file in there called Localization.csv. This file will define all of your mod localization strings. Here you can add both English texts and other languages.

The file is encoded as Tab Separated Values (TSV). Initialize the file with the following content (Choose one of these two):

{% code title="Reduced set" %}
```
Key	Type	Desc	English	German	Japanese	Korean	Spanish	Chinese (Simplified)	Thai
```
{% endcode %}

{% code title="All languages" %}
```
Key	Type	Desc	English	German	French (France)	Portuguese (Brazil)	Italian (Italy)	Japanese	Korean	Russian	Spanish	Ukrainian	Chinese (Simplified)	Chinese (Traditional)	Thai
```
{% endcode %}

From the next line starts the actual content which needs to be tab separated. I would recommend to get a good CSV editor. One good option is [Rons Data Edit](https://ronsplace.eu/products/ronsdataedit), which can be used for free.

Add following content:

* Key: `Items/ExampleMod:ExampleItem` , English: `Example Item`
* &#x20;Key: `Items/ExampleMod:ExampleItemDesc`, English: `My first item.`

Fill other fields on your own discretion. Please note that `ExampleMod:ExampleItem` here is your Object Name as set in ObjectAuthoring.

### Trying Out Items In-Game

Once you have created your new item you will need to get it to test the mod.

Unfortunately, at the moment, the only way to get an item if it wasn't explicitly added to a workbench, drop table or other source is by using cheats like Chat Commands.&#x20;

{% embed url="https://mod.io/g/corekeeper/m/chatcommands3" %}

With Chat Commands you can acquire any item like so: `/give ExampleMod:ExampleItem [optional amount]`
