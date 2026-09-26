---
title: PathfinderAPI/BaseGameFixes/KillExeCheckIdentifierName.cs

---

# PathfinderAPI/BaseGameFixes/KillExeCheckIdentifierName.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::BaseGameFixes::KillExeCheckIdentifierName](../Classes/class_pathfinder_1_1_base_game_fixes_1_1_kill_exe_check_identifier_name/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
public static class KillExeCheckIdentifierName
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(SAKillExe), nameof(SAKillExe.Trigger))]
    internal static void SAKillExeTriggerIL(ILContext il)
    {
        ILCursor c = new ILCursor(il);
        
        // if (oS.exes[i].name.ToLower().Contains(ExeName.ToLower()))
        c.GotoNext(MoveType.After,
            // (...)
            x => x.MatchLdfld(AccessTools.Field(typeof(SAKillExe), nameof(SAKillExe.ExeName))),
            x => x.MatchCallvirt(AccessTools.Method(typeof(string), nameof(string.ToLower))),
            x => x.MatchCallvirt(AccessTools.Method(typeof(string), nameof(string.Contains), new Type[]{ typeof(string) })),
            x => x.MatchLdcI4(0),
            x => x.MatchCeq()
        );
        c.Emit(OpCodes.Ldarg_0);
        c.Emit(OpCodes.Ldloc_0);
        c.Emit(OpCodes.Ldloc_1);
        c.EmitDelegate<Func<SAKillExe, OS, int, bool>>((__instance, oS, i) =>
            oS.exes[i].IdentifierName.ToLower().Contains(__instance.ExeName.ToLower())
        );
        c.Emit(OpCodes.Ldc_I4_0);
        c.Emit(OpCodes.Ceq);
        c.Emit(OpCodes.And);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
