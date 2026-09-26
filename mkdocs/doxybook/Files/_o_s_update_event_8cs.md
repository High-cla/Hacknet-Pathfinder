---
title: PathfinderAPI/Event/Gameplay/OSUpdateEvent.cs

---

# PathfinderAPI/Event/Gameplay/OSUpdateEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Gameplay](../Namespaces/namespace_pathfinder_1_1_event_1_1_gameplay/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Gameplay::OSUpdateEvent](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_o_s_update_event/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Microsoft.Xna.Framework;

namespace Pathfinder.Event.Gameplay;

[HarmonyPatch]
public class OSUpdateEvent : PathfinderEvent
{
    public OS OS { get; }
    public GameTime GameTime { get; }

    public OSUpdateEvent(OS os, GameTime gameTime)
    {
        OS = os;
        GameTime = gameTime;
    }

    [HarmonyPostfix]
    [HarmonyPatch(typeof(OS), nameof(OS.Update))]
    private static void OSUpdatePostfix(OS __instance, GameTime gameTime)
    {
        var osUpdate = new OSUpdateEvent(__instance, gameTime);
        EventManager<OSUpdateEvent>.InvokeAll(osUpdate);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
