---
title: PathfinderAPI/BaseGameFixes/ClearPostLoadActions.cs

---

# PathfinderAPI/BaseGameFixes/ClearPostLoadActions.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal class ClearPostLoadActions
{
    [HarmonyPostfix]
    [HarmonyPatch(typeof(OS), nameof(OS.LoadContent))]
    internal static void ClearComputerPostLoadActionsPostfix()
    {
        ComputerLoader.postAllLoadedActions = null;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
