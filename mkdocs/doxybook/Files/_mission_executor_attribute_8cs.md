---
title: PathfinderAPI/Meta/Load/MissionExecutorAttribute.cs

---

# PathfinderAPI/Meta/Load/MissionExecutorAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::MissionExecutorAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_mission_executor_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Replacements;
using Pathfinder.Util.XML;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class MissionExecutorAttribute : BaseAttribute
{
    public string Element { get; }
    public ParseOption ParseOptions { get; set; }

    public MissionExecutorAttribute(string element, ParseOption parseOptions = ParseOption.None)
    {
        Element = element;
        ParseOptions = parseOptions;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        MissionLoader.RegisterExecutor((Type)targettedInfo, Element, ParseOptions);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
