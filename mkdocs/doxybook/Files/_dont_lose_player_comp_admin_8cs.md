---
title: PathfinderAPI/BaseGameFixes/DontLosePlayerCompAdmin.cs

---

# PathfinderAPI/BaseGameFixes/DontLosePlayerCompAdmin.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal static class DontLosePlayerCompAdmin
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(SAChangeIP), nameof(SAChangeIP.Trigger))]
    internal static void NotifyOSOfPlayerCompIPChange(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        c.GotoNext(MoveType.After,
            x => x.MatchLdloc(1),
            x => x.MatchLdarg(0),
            x => x.MatchLdfld(AccessTools.Field(typeof(SAChangeIP), nameof(SAChangeIP.NewIP))),
            x => x.MatchStfld(AccessTools.Field(typeof(Computer), nameof(Computer.ip)))
        );

        c.Emit(OpCodes.Ldarg_1);
        c.Emit(OpCodes.Castclass, typeof(OS));
        c.Emit(OpCodes.Ldloc_1);
        c.EmitDelegate<System.Action<OS, Computer>>((os, comp) =>
        {
            if (comp.idName == "playerComp")
            {
                os.thisComputerIPReset();
            }
        });
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
