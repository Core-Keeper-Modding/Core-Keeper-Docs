# Unique Names and IDs

## **Object Names** and **Tileset Ids**

Unique string identifiers used to distinguish modded content.

These IDs must be unique across your mod AND all other mods. The easiest way to do that is to follow this naming pattern: `ModName:ContentNameHere`. This will reduce the possibility of cross-mod conflicts to pretty much zero.

## Object IDs

Not to be confused with Object Names, Object IDs are integer identifiers used to refer to base-game items. You can find a list of all item IDs here (TODO). Note that mod content Object Names will be converted into IDs at runtime, but these IDs could change depending on what mods are installed, so never hardcode a modded Object ID.
