---
title: PathfinderAPI/Meta/Load/ExecutableAttribute.cs

---

# PathfinderAPI/Meta/Load/ExecutableAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::ExecutableAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_executable_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Executable;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class ExecutableAttribute : BaseAttribute
{
    public string XmlName { get; }

    public ExecutableAttribute(string xmlName)
    {
        XmlName = xmlName;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        ExecutableManager.RegisterExecutable((Type)targettedInfo, XmlName);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
