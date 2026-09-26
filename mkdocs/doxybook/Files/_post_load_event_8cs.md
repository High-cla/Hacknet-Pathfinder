---
title: PathfinderAPI/Event/BepInEx/PostLoadEvent.cs

---

# PathfinderAPI/Event/BepInEx/PostLoadEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::BepInEx](../Namespaces/namespace_pathfinder_1_1_event_1_1_bep_in_ex/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::BepInEx::PostLoadEvent](../Classes/class_pathfinder_1_1_event_1_1_bep_in_ex_1_1_post_load_event/)**  |




## Source code

```csharp
using BepInEx.Hacknet;
using HarmonyLib;

namespace Pathfinder.Event.BepInEx;

[HarmonyPatch]
public class PostLoadEvent : PathfinderEvent
{
    [HarmonyPostfix]
    [HarmonyPatch(typeof(HacknetPlugin), nameof(HacknetPlugin.PostLoad))]
    private static void OnPluginPostLoad(ref HacknetPlugin __instance)
    {
        var evt = new PostLoadEvent();
        EventManager<PostLoadEvent>.InvokeAssembly(__instance.GetType().Assembly, evt);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
