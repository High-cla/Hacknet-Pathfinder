---
title: PathfinderAPI/Meta/Load/ConditionAttribute.cs

---

# PathfinderAPI/Meta/Load/ConditionAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::ConditionAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_condition_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Action;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class ConditionAttribute : BaseAttribute
{
    public string XmlName { get; }

    public ConditionAttribute(string xmlName)
    {
        this.XmlName = xmlName;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        ConditionManager.RegisterCondition((Type)targettedInfo, XmlName);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
