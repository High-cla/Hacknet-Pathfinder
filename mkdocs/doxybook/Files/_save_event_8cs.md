---
title: PathfinderAPI/Event/Saving/SaveEvent.cs

---

# PathfinderAPI/Event/Saving/SaveEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Saving](../Namespaces/namespace_pathfinder_1_1_event_1_1_saving/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Saving::SaveEvent](../Classes/class_pathfinder_1_1_event_1_1_saving_1_1_save_event/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;

namespace Pathfinder.Event.Saving;

public class SaveEvent : PathfinderEvent
{
    public OS Os { get; }
    public XElement Save { get; }
    public string Filename { get; }

    public SaveEvent(OS os, XElement save, string filename)
    {
        Os = os;
        Save = save;
        Filename = filename;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
