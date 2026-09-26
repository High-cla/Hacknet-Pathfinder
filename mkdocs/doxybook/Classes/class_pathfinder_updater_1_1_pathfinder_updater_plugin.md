---
title: PathfinderUpdater::PathfinderUpdaterPlugin

---

# PathfinderUpdater::PathfinderUpdaterPlugin





Inherits from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| override bool | **[Load](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-load)**() |
| virtual override void | **[PostLoad](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-postload)**()<br>Runs after all plugins have executed their Load method.  |
| void | **[RestartForUpdate](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-restartforupdate)**() |
| async Task | **[PerformUpdateAsync](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-performupdateasync)**() |
| void | **[PerformUpdateCheck](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-performupdatecheck)**() |
| async Task< bool[]> | **[PerformCheckAsync](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#function-performcheckasync)**(bool forceData =false) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| const string | **[ModGUID](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#variable-modguid)**  |
| const string | **[ModName](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#variable-modname)**  |
| [Version](../Files/_hacknet_chainloader_8cs/#using-version) | **[VersionToRequest](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#variable-versiontorequest)**  |
| bool | **[NeedsUpdate](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#variable-needsupdate)**  |
| readonly List< [Updater](../Classes/class_pathfinder_updater_1_1_updater/) > | **[Updaters](../Classes/class_pathfinder_updater_1_1_pathfinder_updater_plugin/#variable-updaters)**  |

## Additional inherited members

**Public Functions inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

|                | Name           |
| -------------- | -------------- |
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
| Harmony | **[HarmonyInstance](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#property-harmonyinstance)**  |


## Public Functions Documentation

### function Load

```csharp
override bool Load()
```


### function PostLoad

```csharp
virtual override void PostLoad()
```

Runs after all plugins have executed their Load method. 

**Reimplements**: [BepInEx::Hacknet::HacknetPlugin::PostLoad](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-postload)


### function RestartForUpdate

```csharp
static void RestartForUpdate()
```


### function PerformUpdateAsync

```csharp
static async Task PerformUpdateAsync()
```


### function PerformUpdateCheck

```csharp
static void PerformUpdateCheck()
```


### function PerformCheckAsync

```csharp
static async Task< bool[]> PerformCheckAsync(
    bool forceData =false
)
```


## Public Attributes Documentation

### variable ModGUID

```csharp
static const string ModGUID = "com.Pathfinder.Updater";
```


### variable ModName

```csharp
static const string ModName = "AutoUpdater";
```


### variable VersionToRequest

```csharp
static Version VersionToRequest = null;
```


### variable NeedsUpdate

```csharp
static bool NeedsUpdate;
```


### variable Updaters

```csharp
static readonly List< Updater > Updaters = new List<Updater>();
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000