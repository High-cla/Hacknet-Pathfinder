---
title: PathfinderAPI/Event/Loading/OSLoadedEvent.cs

---

# PathfinderAPI/Event/Loading/OSLoadedEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Loading](../Namespaces/namespace_pathfinder_1_1_event_1_1_loading/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Loading::OSLoadedEvent](../Classes/class_pathfinder_1_1_event_1_1_loading_1_1_o_s_loaded_event/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;

namespace Pathfinder.Event.Loading;

[HarmonyPatch]
public class OSLoadedEvent : PathfinderEvent
{
    public OS Os { get; }

    public OSLoadedEvent(OS os)
    {
        Os = os;
    }

    [HarmonyPostfix]
    [HarmonyPatch(typeof(OS), nameof(OS.LoadContent))]
    private static void OSLoadPostfix(OS __instance) => EventManager<OSLoadedEvent>.InvokeAll(new OSLoadedEvent(__instance));
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
