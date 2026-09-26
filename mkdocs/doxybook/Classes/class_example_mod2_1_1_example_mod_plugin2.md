---
title: ExampleMod2::ExampleModPlugin2

---

# ExampleMod2::ExampleModPlugin2





Inherits from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| override bool | **[Load](../Classes/class_example_mod2_1_1_example_mod_plugin2/#function-load)**() |
| virtual override bool | **[Unload](../Classes/class_example_mod2_1_1_example_mod_plugin2/#function-unload)**() |
| void | **[TestCommand](../Classes/class_example_mod2_1_1_example_mod_plugin2/#function-testcommand)**(OS os, string[] args) |

## Additional inherited members

**Public Functions inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

|                | Name           |
| -------------- | -------------- |
| virtual void | **[PostLoad](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-postload)**()<br>Runs after all plugins have executed their Load method.  |

**Protected Functions inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

|                | Name           |
| -------------- | -------------- |
| | **[HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-hacknetplugin)**() |

**Public Properties inherited from [BepInEx.Hacknet.HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**

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
override bool Load()
```


### function Unload

```csharp
virtual override bool Unload()
```


**Reimplements**: [BepInEx::Hacknet::HacknetPlugin::Unload](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/#function-unload)


### function TestCommand

```csharp
static void TestCommand(
    OS os,
    string[] args
)
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000