---
title: PathfinderAPI/Meta/Load/SaveExecutorAttribute.cs

---

# PathfinderAPI/Meta/Load/SaveExecutorAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::SaveExecutorAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_save_executor_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Replacements;
using Pathfinder.Util.XML;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class SaveExecutorAttribute : BaseAttribute
{
    public string Element { get; }
    public ParseOption ParseOptions { get; set; }

    public SaveExecutorAttribute(string element, ParseOption parseOptions = ParseOption.None)
    {
        Element = element;
        ParseOptions = parseOptions;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        SaveLoader.RegisterExecutor((Type)targettedInfo, Element, ParseOptions);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
