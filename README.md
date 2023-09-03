# More Ring Slots - Baldurs Gate 3

A Baldurs Gate 3 Mod

Adds more rings slots.

## Description

This mod is a WIP, it does not work yet due to missing a data binding for equipment or registering the "Ring3" item.

## How to add new slots

__Update Public\Game\GUI\Library\CharacterSheetTemplates_k.xamlCharacterSheetTemplates_k.xaml__

Example: On around lines 7417. Adding an additional `LSButton` will add a new slot. This slot will be bound to the Ring2 slot instance. So you will only be updating that data item

```xml
<ls:LSButton Style="{StaticResource newEquipmentSlotStyle}" Panel.ZIndex="{Binding IsSelecting, Converter={StaticResource BoolToIntConverter}, ConverterParameter=20}" DataContext="{Binding Equipment.Ring2}"/>
<ls:LSButton Style="{StaticResource newEquipmentSlotStyle}" Panel.ZIndex="{Binding IsSelecting, Converter={StaticResource BoolToIntConverter}, ConverterParameter=20}" DataContext="{Binding Equipment.Ring2}"/>
```

Attempting to add a new slot like of an unknown "new" equipment type such as `Binding Equipment.Ring3` does not work for some reason. Probably due to the Equipment slots not supporting a Ring3 type. 

Those files are hard to track down...still working on it. Add an issue to this github if you figure it out.

The UI for the rings will show up


## Installing

1. You can directly install this mod via the Public folder route. As this is not stable and does literally nothing, I'll not be deploying a version to nexusmods yet.
2. The top level folder should be ignored. Focus on files inside lib for now. Once the mod is stable it will be turned into a .pak file.