---
title: PathfinderAPI/Meta/Load/HacknetPluginExtensions.cs

---

# PathfinderAPI/Meta/Load/HacknetPluginExtensions.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::HacknetPluginExtensions](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_hacknet_plugin_extensions/)**  |




## Source code

```csharp
using BepInEx.Hacknet;

namespace Pathfinder.Meta.Load;

public static class HacknetPluginExtensions
{
    public static string GetOptionsTag(this HacknetPlugin plugin)
    {
        if(!OptionsTabAttribute.pluginToOptionsTag.TryGetValue(plugin, out var tag))
            return null;
        return tag;
    }

    public static bool HasOptionsTag(this HacknetPlugin plugin)
    {
        return OptionsTabAttribute.pluginToOptionsTag.ContainsKey(plugin);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
