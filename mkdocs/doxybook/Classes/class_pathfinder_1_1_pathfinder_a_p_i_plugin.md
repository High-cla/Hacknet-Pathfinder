---
title: Pathfinder::PathfinderAPIPlugin

---

# Pathfinder::PathfinderAPIPlugin





Inherits from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| override bool | **[Load](../Classes/class_pathfinder_1_1_pathfinder_a_p_i_plugin/#function-load)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| const string | **[ModGUID](../Classes/class_pathfinder_1_1_pathfinder_a_p_i_plugin/#variable-modguid)**  |
| const string | **[ModName](../Classes/class_pathfinder_1_1_pathfinder_a_p_i_plugin/#variable-modname)**  |
| readonly bool | **[GameIsSteamVersion](../Classes/class_pathfinder_1_1_pathfinder_a_p_i_plugin/#variable-gameissteamversion)**  |

## Additional inherited members

**Public Functions inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

|                | Name           |
| -------------- | -------------- |
| virtual void | **[PostLoad](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-postload)**()<br>Runs after all plugins have executed their Load method.  |
| virtual bool | **[Unload](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-unload)**() |

**Protected Functions inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

|                | Name           |
| -------------- | -------------- |
| | **[HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-hacknetplugin)**() |

**Public Properties inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

|                | Name           |
| -------------- | -------------- |
| ManualLogSource | **[Log](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-log)**  |
| bool | **[InstalledGlobally](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-installedglobally)**  |
| ConfigFile | **[UserConfig](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-userconfig)** <br>If this plugin is installed in an extension, holds a ConfigFile to be edited by the extension player.    Otherwise, if its installed globally, holds the value `null`.     For the extension developer's ConfigFile, see Config.  |


## Public Functions Documentation

### function Load

```csharp
override bool Load()
```


## Public Attributes Documentation

### variable ModGUID

```csharp
static const string ModGUID = "com.Pathfinder.API";
```


### variable ModName

```csharp
static const string ModName = "PathfinderAPI";
```


### variable GameIsSteamVersion

```csharp
static readonly bool GameIsSteamVersion = typeof(Hacknet.PlatformAPI.Storage.SteamCloudStorageMethod).GetField("deserialized") != null;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000