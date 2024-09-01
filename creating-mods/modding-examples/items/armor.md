# Armor

## Follow the Item Guide

Follow the steps in the generic item guide first to define the other required properties of your item.

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

## Armor

{% hint style="warning" %}
The [CoreLib.Equipment submodule](../../modding-libraries/corelib.md) is required for this guide section.
{% endhint %}

To make armor you need to:

* Set the `ObjectType` to armor type
* Add `DurabilityAuthoring`, `ModEquipmentSkinAuthoring`, `GivesConditionsWhenEquipedAuthoring` and `LevelAuthoring` component authorings and configure them correctly

Make a armor spite sheet. Examples of such sheets can be found in the Unity Editor. Now assign your texture to `ModEquipmentSkinAuthoring` (CoreLib feature). The component will automatically set everything up.
