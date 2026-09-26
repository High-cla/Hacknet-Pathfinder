---
title: BepInEx::Hacknet::HacknetPlugin

---

# BepInEx::Hacknet::HacknetPlugin





Inherited by [ExampleMod2.ExampleModPlugin2](../Classes/class_example_mod2_1_1_example_mod_plugin2/), [Pathfinder.PathfinderAPIPlugin](../Classes/class_pathfinder_1_1_pathfinder_a_p_i_plugin/), [PathfinderUpdater.PathfinderUpdaterPlugin](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[Load](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-load)**() |
| virtual void | **[PostLoad](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-postload)**()<br>Runs after all plugins have executed their Load method.  |
| virtual bool | **[Unload](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-unload)**() |

## Protected Functions

|                | Name           |
| -------------- | -------------- |
| | **[HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-hacknetplugin)**() |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| ManualLogSource | **[Log](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-log)**  |
| bool | **[InstalledGlobally](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-installedglobally)**  |
| ConfigFile | **[Config](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-config)** <br>If this plugin is installed in an extension, holds a ConfigFile to be edited by the extension developer.    Otherwise, if its installed globally, holds a ConfigFile to be edited by the user.     For the extension player's ConfigFile, see UserConfig.  |
| ConfigFile | **[UserConfig](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-userconfig)** <br>If this plugin is installed in an extension, holds a ConfigFile to be edited by the extension player.    Otherwise, if its installed globally, holds the value `null`.     For the extension developer's ConfigFile, see Config.  |
| Harmony | **[HarmonyInstance](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-harmonyinstance)**  |

## Public Functions Documentation

### function Load

```csharp
bool Load()
```


### function PostLoad

```csharp
virtual void PostLoad()
```

Runs after all plugins have executed their Load method. 

**Reimplemented by**: [PathfinderUpdater::PathfinderUpdaterPlugin::PostLoad](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-postload)


### function Unload

```csharp
virtual bool Unload()
```


**Reimplemented by**: [ExampleMod2::ExampleModPlugin2::Unload](../Classes/class_example_mod2_1_1_example_mod_plugin2/#function-unload)


## Protected Functions Documentation

### function HacknetPlugin

```csharp
HacknetPlugin()
```


## Public Property Documentation

### property Log

```csharp
ManualLogSource Log;
```


### property InstalledGlobally

```csharp
bool InstalledGlobally;
```


### property Config

```csharp
ConfigFile Config;
```

If this plugin is installed in an extension, holds a ConfigFile to be edited by the extension developer.    Otherwise, if its installed globally, holds a ConfigFile to be edited by the user.     For the extension player's ConfigFile, see UserConfig. 

### property UserConfig

```csharp
ConfigFile UserConfig;
```

If this plugin is installed in an extension, holds a ConfigFile to be edited by the extension player.    Otherwise, if its installed globally, holds the value `null`.     For the extension developer's ConfigFile, see Config. 

### property HarmonyInstance

```csharp
Harmony HarmonyInstance;
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000