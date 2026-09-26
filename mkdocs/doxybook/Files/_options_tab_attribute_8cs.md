---
title: PathfinderAPI/Meta/Load/OptionsTabAttribute.cs

---

# PathfinderAPI/Meta/Load/OptionsTabAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::OptionsTabAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_options_tab_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class)]
public class OptionsTabAttribute : BaseAttribute
{
    internal static readonly Dictionary<HacknetPlugin, string> pluginToOptionsTag = new Dictionary<HacknetPlugin, string>();

    public string Tag { get; }

    public OptionsTabAttribute(string tag)
    {
        this.Tag = tag;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        pluginToOptionsTag.Add(plugin, Tag);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
