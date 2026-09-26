---
title: PathfinderAPI/BaseGameFixes/FixExtensionTests.cs

---

# PathfinderAPI/BaseGameFixes/FixExtensionTests.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |
| **[Hacknet::Misc](../Namespaces/namespace_hacknet_1_1_misc/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::BaseGameFixes::FixExtensionTests](../Classes/class_pathfinder_1_1_base_game_fixes_1_1_fix_extension_tests/)**  |




## Source code

```csharp
using Hacknet;
using Hacknet.Extensions;
using Hacknet.Misc;
using HarmonyLib;
using MonoMod.Cil;
using Mono.Cecil.Cil;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
public static class FixExtensionTests
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(ExtensionTests), nameof(ExtensionTests.TestExtensionForRuntime))]
    [HarmonyPatch(typeof(ExtensionTests), nameof(ExtensionTests.TestExtensionMission))]
    internal static void TestMissionStartingMissionNONEFix(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        // string _text = TestSuite.TestMission(ExtensionLoader.ActiveExtensionInfo.FolderPath + "/" + ExtensionLoader.ActiveExtensionInfo.StartingMissionPath, _os);
        c.GotoNext(MoveType.After,
            x => x.MatchLdsfld(AccessTools.Field(typeof(ExtensionLoader), nameof(ExtensionLoader.ActiveExtensionInfo))),
            x => x.MatchLdfld(AccessTools.Field(typeof(ExtensionInfo), nameof(ExtensionInfo.FolderPath))),
            x => x.MatchLdstr("/"),
            x => x.MatchLdsfld(AccessTools.Field(typeof(ExtensionLoader), nameof(ExtensionLoader.ActiveExtensionInfo))),
            x => x.MatchLdfld(AccessTools.Field(typeof(ExtensionInfo), nameof(ExtensionInfo.StartingMissionPath))),
            x => x.MatchCall(AccessTools.Method(typeof(string), nameof(string.Concat), new Type[] { typeof(string), typeof(string), typeof(string) })),
            _ => true,
            x => x.MatchCall(AccessTools.Method(typeof(TestSuite), nameof(TestSuite.TestMission))),
            x => x.MatchStloc(out int _)
        );
        c.Index--;
        ILLabel labelDontTestStartingMission = c.MarkLabel();
        c.Index -= 7;
        ILLabel labelTestStartingMission = c.MarkLabel();
        c.MoveBeforeLabels();

        c.Emit(OpCodes.Dup);
        c.EmitDelegate<Func<ExtensionInfo, bool>>(info =>
            info.StartingMissionPath == null
        );
        c.Emit(OpCodes.Brfalse, labelTestStartingMission);
        c.Emit(OpCodes.Pop);
        c.Emit(OpCodes.Ldstr, "");
        c.Emit(OpCodes.Br, labelDontTestStartingMission);
    }
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(ExtensionInfo), nameof(ExtensionInfo.VerifyExtensionInfo))]
    internal static void ExtensionInfoStartingMissionNONEFix(ILContext il)
    {
        ILCursor c = new ILCursor(il);
        // if (!File.Exists(info.FolderPath + "/" + info.StartingMissionPath))
        c.GotoNext(MoveType.After,
            x => x.MatchLdarg(0),
            x => x.MatchLdfld(AccessTools.Field(typeof(ExtensionInfo), nameof(ExtensionInfo.FolderPath))),
            x => x.MatchLdstr("/"),
            x => x.MatchLdarg(0),
            x => x.MatchLdfld(AccessTools.Field(typeof(ExtensionInfo), nameof(ExtensionInfo.StartingMissionPath))),
            x => x.MatchCall(AccessTools.Method(typeof(string), nameof(string.Concat), new Type[] { typeof(string), typeof(string), typeof(string) })),
            x => x.MatchCall(AccessTools.Method(typeof(File), nameof(File.Exists))),
            x => x.MatchStloc(3),
            x => x.MatchLdloc(3),
            x => x.MatchBrtrue(out ILLabel _)
        );
        c.Index--;
        c.Emit(OpCodes.Ldarg_0);
        c.EmitDelegate<Func<bool, ExtensionInfo, bool>>((b, info) =>
            b || info.StartingMissionPath == null
        );
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
