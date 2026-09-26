---
title: PathfinderAPI/Event/BepInEx/LoadEvent.cs

---

# PathfinderAPI/Event/BepInEx/LoadEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::BepInEx](../Namespaces/namespace_pathfinder_1_1_event_1_1_bep_in_ex/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::BepInEx::LoadEvent](../Classes/class_pathfinder_1_1_event_1_1_bep_in_ex_1_1_load_event/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using HarmonyLib;

namespace Pathfinder.Event.BepInEx;

[HarmonyPatch]
public class LoadEvent : PathfinderEvent
{
    [HarmonyPostfix]
    [HarmonyPatch(typeof(HacknetChainloader), nameof(HacknetChainloader.LoadPlugin))]
    private static void OnPluginLoad(ref HacknetChainloader __instance, ref HacknetPlugin __result, Assembly pluginAssembly)
    {
        var evt = new LoadEvent();
        EventManager<LoadEvent>.InvokeAssembly(pluginAssembly, evt);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
