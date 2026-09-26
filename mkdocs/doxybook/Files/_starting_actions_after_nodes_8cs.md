---
title: PathfinderAPI/BaseGameFixes/StartingActionsAfterNodes.cs

---

# PathfinderAPI/BaseGameFixes/StartingActionsAfterNodes.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using Hacknet;
using Hacknet.Extensions;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal static class StartingActionsAfterNodes
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(ExtensionLoader), nameof(ExtensionLoader.LoadNewExtensionSession))]
    internal static void FixStartingActionsIL(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        c.GotoNext(MoveType.Before,
            x => x.MatchCallOrCallvirt(AccessTools.Method(typeof(RunnableConditionalActions), nameof(RunnableConditionalActions.LoadIntoOS)))
        );

        c.Remove();
        c.Emit(OpCodes.Pop);
        c.Emit(OpCodes.Pop);
    }

    [HarmonyPostfix]
    [HarmonyPatch(typeof(OS), nameof(OS.LoadContent))]
    internal static void RunStartingActions(ref OS __instance)
    {
        if (!OS.WillLoadSave && Settings.IsInExtensionMode && ExtensionLoader.ActiveExtensionInfo.StartingActionsPath != null)
            RunnableConditionalActions.LoadIntoOS(ExtensionLoader.ActiveExtensionInfo.StartingActionsPath, __instance);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
