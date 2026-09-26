---
title: PathfinderAPI/Event/BepInEx/UnloadEvent.cs

---

# PathfinderAPI/Event/BepInEx/UnloadEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::BepInEx](../Namespaces/namespace_pathfinder_1_1_event_1_1_bep_in_ex/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::BepInEx::UnloadEvent](../Classes/class_pathfinder_1_1_event_1_1_bep_in_ex_1_1_unload_event/)**  |




## Source code

```csharp
using BepInEx.Hacknet;
using HarmonyLib;

namespace Pathfinder.Event.BepInEx;

[HarmonyPatch]
public class UnloadEvent : PathfinderEvent
{
    [HarmonyPrefix]
    [HarmonyPatch(typeof(HacknetPlugin), nameof(HacknetPlugin.Unload))]
    private static void OnPluginUnload(ref HacknetPlugin __instance)
    {
        var evt = new UnloadEvent();
        EventManager<UnloadEvent>.InvokeAssembly(__instance.GetType().Assembly, evt);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
