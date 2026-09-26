---
title: PathfinderAPI/BaseGameFixes/AutoClearMissionsOnSingleComplete.cs

---

# PathfinderAPI/BaseGameFixes/AutoClearMissionsOnSingleComplete.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;
using Hacknet;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal static class AutoClearMissionsOnSingleComplete
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(DLCHubServer), nameof(DLCHubServer.PlayerAttemptCompleteMission))]
    internal static void DontClearMissionsOnCompleteIL(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        c.GotoNext(MoveType.AfterLabel,
            x => x.MatchLdarg(0),
            x => x.MatchLdfld(AccessTools.Field(typeof(Hacknet.Daemon), nameof(Hacknet.Daemon.os))),
            x => x.MatchCallvirt(AccessTools.Method(typeof(OS), nameof(OS.saveGame)))
        );

        c.Emit(OpCodes.Ldarg_0);
        c.Emit(OpCodes.Ldfld, AccessTools.Field(typeof(DLCHubServer), nameof(DLCHubServer.AutoClearMissionsOnSingleComplete)));
        var branch = c.Emit(OpCodes.Brtrue, c.DefineLabel()).Prev;
        c.Emit(OpCodes.Ldarg_0);
        c.Emit(OpCodes.Ldloc_0);
        c.Emit(OpCodes.Stfld, AccessTools.Field(typeof(DLCHubServer), nameof(DLCHubServer.ActiveMissions)));

        ((ILLabel) branch.Operand).Target = c.Next;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
