---
title: PathfinderAPI/Event/Loading/SaveComputerLoadedEvent.cs

---

# PathfinderAPI/Event/Loading/SaveComputerLoadedEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Loading](../Namespaces/namespace_pathfinder_1_1_event_1_1_loading/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Loading::SaveComputerLoadedEvent](../Classes/class_pathfinder_1_1_event_1_1_loading_1_1_save_computer_loaded_event/)**  |




## Source code

```csharp
using HarmonyLib;
using Hacknet;
using Pathfinder.Util.XML;

namespace Pathfinder.Event.Loading;

[HarmonyPatch]
public class SaveComputerLoadedEvent : PathfinderEvent
{
    public OS Os { get; }
    public Computer Comp { get; }
    public ElementInfo Info { get; }

    public SaveComputerLoadedEvent(OS os, Computer comp, ElementInfo info)
    {
        Os = os;
        Comp = comp;
        Info = info;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
