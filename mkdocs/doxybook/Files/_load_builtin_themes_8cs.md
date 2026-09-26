---
title: PathfinderAPI/BaseGameFixes/LoadBuiltinThemes.cs

---

# PathfinderAPI/BaseGameFixes/LoadBuiltinThemes.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Mono.Cecil;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal class LoadBuiltinThemes {
    [HarmonyILManipulator]
    [HarmonyPatch(typeof (Hacknet.Extensions.ExtensionLoader), "LoadNewExtensionSession")]
    internal static void PatchEnumFind(ILContext il) {
        ILCursor cursor = new ILCursor(il);

        cursor.GotoNext(MoveType.Before,
            x => x.MatchLdcI4(0),
            x => x.MatchStloc(9),
            x => x.MatchNop(),
            x => {
                if(!x.MatchLdtoken(out IMetadataTokenProvider metadata))
                    return false;
                if(!(metadata is TypeReference typeRef))
                    return false;
                return typeRef.FullName == "Hacknet.OSTheme";
            },
            x => x.MatchCall(typeof(Type), "GetTypeFromHandle"),
            x => x.MatchCall(typeof(Enum), "GetValues")
        );
        cursor.RemoveRange(57); // whew
        /* arg1: `info.Theme` */
        cursor.Emit(OpCodes.Ldarg_0); /* info */
        cursor.Emit(OpCodes.Ldfld, AccessTools.Field(typeof(Hacknet.Extensions.ExtensionInfo), "Theme"));
        /* arg2: `true` */
        cursor.Emit(OpCodes.Ldc_I4_1);
        /* arg3: `out theme` */
        cursor.Emit(OpCodes.Ldloca, 8);
        /* call: `Enum.TryParse<OSTheme>(string: info.Theme, bool: true, out OSTheme: theme)` */
        cursor.Emit(OpCodes.Call, AccessTools.FirstMethod(typeof(Enum), x => x.Name == "TryParse" && x.GetParameters().Length == 3 && x.GetGenericArguments().Length == 1).MakeGenericMethod(typeof(OSTheme)));
        cursor.Emit(OpCodes.Dup);
        cursor.Emit(OpCodes.Stloc, 9);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
