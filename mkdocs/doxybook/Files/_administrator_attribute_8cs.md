---
title: PathfinderAPI/Meta/Load/AdministratorAttribute.cs

---

# PathfinderAPI/Meta/Load/AdministratorAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::AdministratorAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_administrator_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Administrator;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class AdministratorAttribute : BaseAttribute
{
    public string XmlName { get; }

    public AdministratorAttribute()
    {
    }
    public AdministratorAttribute(string xmlName)
    {
        this.XmlName = xmlName;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        if (XmlName == null)
            AdministratorManager.RegisterAdministrator((Type)targettedInfo);
        else
            AdministratorManager.RegisterAdministrator((Type)targettedInfo, XmlName);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
