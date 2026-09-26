---
title: PathfinderAPI/BaseGameFixes/RandomIPNoRepeats.cs

---

# PathfinderAPI/BaseGameFixes/RandomIPNoRepeats.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Pathfinder.Util;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal static class RandomIPNoRepeats
{
    [HarmonyPrefix]
    [HarmonyPatch(typeof(NetworkMap), nameof(NetworkMap.generateRandomIP))]
    internal static bool GenerateRandomIPReplacement(out string __result)
    {
        while (true)
        {
            var ip = Utils.random.Next(254) + 1 + "." + (Utils.random.Next(254) + 1) + "." + (Utils.random.Next(254) + 1) + "." + (Utils.random.Next(254) + 1);
            if (ComputerLookup.FindByIp(ip, false) == null)
            {
                __result = ip;
                return false;
            }
        }
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
