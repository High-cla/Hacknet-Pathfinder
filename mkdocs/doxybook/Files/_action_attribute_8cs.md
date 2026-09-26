---
title: PathfinderAPI/Meta/Load/ActionAttribute.cs

---

# PathfinderAPI/Meta/Load/ActionAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::ActionAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_action_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Action;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class ActionAttribute : BaseAttribute
{
    public string XmlName { get; }

    public ActionAttribute(string xmlName)
    {
        this.XmlName = xmlName;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        ActionManager.RegisterAction((Type)targettedInfo, XmlName);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
