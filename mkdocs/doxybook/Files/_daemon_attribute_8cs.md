---
title: PathfinderAPI/Meta/Load/DaemonAttribute.cs

---

# PathfinderAPI/Meta/Load/DaemonAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::DaemonAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_daemon_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Daemon;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Class)]
public class DaemonAttribute : BaseAttribute
{
    public DaemonAttribute()
    {
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        DaemonManager.RegisterDaemon((Type)targettedInfo);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
