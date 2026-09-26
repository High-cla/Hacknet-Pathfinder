---
title: PathfinderAPI/BaseGameFixes/FlickeringTextReportNull.cs

---

# PathfinderAPI/BaseGameFixes/FlickeringTextReportNull.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |
| **[Hacknet::Effects](../Namespaces/namespace_hacknet_1_1_effects/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::BaseGameFixes::FlickeringTextReportNull](../Classes/class_pathfinder_1_1_base_game_fixes_1_1_flickering_text_report_null/)**  |




## Source code

```csharp
using System.Reflection;
using Hacknet.Effects;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
public static class FlickeringTextReportNull {
    [HarmonyPatch(typeof(FlickeringTextEffect), nameof(FlickeringTextEffect.GetReportString))]
    [HarmonyILManipulator]
    private static void GetReportStringManipulator(ILContext context, ILLabel retLabel) {
        ILCursor cursor = new(context);

        ILLabel unskipLabel = context.DefineLabel();
        cursor.Emit(OpCodes.Ldsfld, typeof(FlickeringTextEffect).GetField(nameof(FlickeringTextEffect.LinedItemTarget), BindingFlags.Static | BindingFlags.Public));
        cursor.Emit(OpCodes.Brtrue, unskipLabel);
        cursor.Emit(OpCodes.Ldstr, "FlickeringTextEffect was not used in this execution.");
        cursor.Emit(OpCodes.Br, retLabel);
        unskipLabel.Target = cursor.Next;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
