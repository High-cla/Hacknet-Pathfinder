---
title: PathfinderAPI/Event/PathfinderEvent.cs

---

# PathfinderAPI/Event/PathfinderEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)**  |




## Source code

```csharp
namespace Pathfinder.Event;

public abstract class PathfinderEvent
{
    internal bool cancelled = false;
    public bool Cancelled { 
        get
        {
            return cancelled;
        }
        set
        {
            cancelled |= value;
        }
    }
    public bool Thrown { get; internal set; } = false;
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
