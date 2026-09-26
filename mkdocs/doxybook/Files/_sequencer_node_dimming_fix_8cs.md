---
title: PathfinderAPI/BaseGameFixes/SequencerNodeDimmingFix.cs

---

# PathfinderAPI/BaseGameFixes/SequencerNodeDimmingFix.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::BaseGameFixes::SequencerNodeDimmingFix](../Classes/class_pathfinder_1_1_base_game_fixes_1_1_sequencer_node_dimming_fix/)**  |




## Source code

```csharp
using Hacknet;

using HarmonyLib;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
public class SequencerNodeDimmingFix
{
    [HarmonyPostfix]
    [HarmonyPatch(typeof(ExtensionSequencerExe), "Killed")]
    static void FixSequencerNodeDimming(ExtensionSequencerExe __instance)
    {
        // This fixes a bug where nodes would continue to be dimmed after the sequencer is killed
        __instance.os.netMap.DimNonConnectedNodes = false;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
