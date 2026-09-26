---
title: PathfinderAPI/Event/Saving/SaveComputerEvent.cs

---

# PathfinderAPI/Event/Saving/SaveComputerEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Saving](../Namespaces/namespace_pathfinder_1_1_event_1_1_saving/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Saving::SaveComputerEvent](../Classes/class_pathfinder_1_1_event_1_1_saving_1_1_save_computer_event/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;

namespace Pathfinder.Event.Saving;

public class SaveComputerEvent : PathfinderEvent
{
    public OS Os { get; }
    public Computer Comp { get; }
    public XElement Element { get; set; }

    public SaveComputerEvent(OS os, Computer comp, XElement element)
    {
        Os = os;
        Comp = comp;
        Element = element;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
