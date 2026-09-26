---
title: PathfinderAPI/Mission/PathfinderGoal.cs

---

# PathfinderAPI/Mission/PathfinderGoal.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Mission](../Namespaces/namespace_pathfinder_1_1_mission/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Mission::PathfinderGoal](../Classes/class_pathfinder_1_1_mission_1_1_pathfinder_goal/)**  |




## Source code

```csharp
using Hacknet.Mission;
using Pathfinder.Util;
using Pathfinder.Util.XML;

namespace Pathfinder.Mission;

public abstract class PathfinderGoal : MisisonGoal
{
    public virtual void LoadFromXML(ElementInfo info)
    {
        XMLStorageAttribute.ReadFromElement(info, this);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
