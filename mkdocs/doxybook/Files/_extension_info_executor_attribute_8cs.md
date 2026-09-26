---
title: PathfinderAPI/Meta/Load/ExtensionInfoExecutorAttribute.cs

---

# PathfinderAPI/Meta/Load/ExtensionInfoExecutorAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::ExtensionInfoExecutorAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_extension_info_executor_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Replacements;
using Pathfinder.Util.XML;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class ExtensionInfoExecutorAttribute : BaseAttribute
{
    public string Element { get; }
    public ParseOption ParseOptions { get; set; }

    public ExtensionInfoExecutorAttribute(string element, ParseOption parseOptions = ParseOption.None)
    {
        Element = element;
        ParseOptions = parseOptions;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        ExtensionInfoLoader.RegisterExecutor((Type)targettedInfo, Element, ParseOptions);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
