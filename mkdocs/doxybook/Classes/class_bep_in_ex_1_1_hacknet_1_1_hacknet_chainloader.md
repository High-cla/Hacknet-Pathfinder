---
title: BepInEx::Hacknet::HacknetChainloader

---

# BepInEx::Hacknet::HacknetChainloader





Inherits from BaseChainloader< HacknetPlugin >

## Public Functions

|                | Name           |
| -------------- | -------------- |
| override void | **[Initialize](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#function-initialize)**(string gameExePath =null) |
| override [HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/) | **[LoadPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#function-loadplugin)**(PluginInfo pluginInfo, Assembly pluginAssembly) |
| override void | **[Execute](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#function-execute)**() |

## Protected Functions

|                | Name           |
| -------------- | -------------- |
| override IList< PluginInfo > | **[DiscoverPlugins](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#function-discoverplugins)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| const string | **[VERSION](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#variable-version)**  |
| readonly [Version](../Files/_hacknet_chainloader_8cs/#using-version) | **[Version](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#variable-version)**  |
| [HacknetChainloader](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/) | **[Instance](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_chainloader/#variable-instance)**  |

## Public Functions Documentation

### function Initialize

```csharp
override void Initialize(
    string gameExePath =null
)
```


### function LoadPlugin

```csharp
override HacknetPlugin LoadPlugin(
    PluginInfo pluginInfo,
    Assembly pluginAssembly
)
```


### function Execute

```csharp
override void Execute()
```


## Protected Functions Documentation

### function DiscoverPlugins

```csharp
override IList< PluginInfo > DiscoverPlugins()
```


## Public Attributes Documentation

### variable VERSION

```csharp
static const string VERSION = "5.4.1";
```


### variable Version

```csharp
static readonly Version Version = Version.Parse(VERSION);
```


### variable Instance

```csharp
static HacknetChainloader Instance;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000