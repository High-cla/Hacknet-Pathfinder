---
title: PathfinderAPI/Event/Pathfinder/BuildAutocompletesEvent.cs

---

# PathfinderAPI/Event/Pathfinder/BuildAutocompletesEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Pathfinder](../Namespaces/namespace_pathfinder_1_1_event_1_1_pathfinder/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Pathfinder::BuildAutocompletesEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_1_1_build_autocompletes_event/)**  |




## Source code

```csharp
namespace Pathfinder.Event.Pathfinder;

public class BuildAutocompletesEvent : PathfinderEvent
{
    public List<string> Autocompletes { get; set; }

    public BuildAutocompletesEvent(List<string> autocompletes)
    {
        Autocompletes = autocompletes;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
