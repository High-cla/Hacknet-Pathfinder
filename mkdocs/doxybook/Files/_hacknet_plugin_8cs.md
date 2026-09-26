---
title: BepInEx.Hacknet/HacknetPlugin.cs

---

# BepInEx.Hacknet/HacknetPlugin.cs



## Namespaces

| Name           |
| -------------- |
| **[BepInEx](../Namespaces/namespace_bep_in_ex/)**  |
| **[BepInEx::Hacknet](../Namespaces/namespace_bep_in_ex_1_1_hacknet/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[BepInEx::Hacknet::HacknetPlugin](../Classes/class_bep_in_ex_1_1_hacknet_1_1_hacknet_plugin/)**  |

## Types

|                | Name           |
| -------------- | -------------- |
| using global::Hacknet | **[HN](../Files/_hacknet_plugin_8cs/#using-hn)**  |

## Types Documentation

### using HN

```csharp
using HN =  global::Hacknet;
```





## Source code

```csharp
using BepInEx.Logging;
using BepInEx.Configuration;
using HarmonyLib;
using Hacknet.Extensions;
using HN = global::Hacknet;

namespace BepInEx.Hacknet;

public abstract class HacknetPlugin
{
    protected HacknetPlugin()
    {
        var metadata = MetadataHelper.GetMetadata(this);

        HarmonyInstance = new Harmony("BepInEx.Plugin." + metadata.GUID);

        Log = Logger.CreateLogSource(metadata.Name);

        InstalledGlobally = !HN.Settings.IsInExtensionMode;

        Config = new ConfigFile(Path.Combine(Paths.ConfigPath, metadata.GUID + ".cfg"), false, metadata);

        if (!InstalledGlobally)
            UserConfig = new ConfigFile(
                Path.Combine("BepInEx/config/", ExtensionLoader.ActiveExtensionInfo.GetFoldersafeName(), metadata.GUID + ".cfg"),
                false,
                metadata
            );
    }

    public ManualLogSource Log { get; }

    public bool InstalledGlobally { get; }

    public ConfigFile Config { get; }
    public ConfigFile UserConfig { get; }

    public Harmony HarmonyInstance { get; set; }

    public abstract bool Load();

    public virtual void PostLoad() {}

    public virtual bool Unload()
    {
        HarmonyInstance.UnpatchSelf();
        return true;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
