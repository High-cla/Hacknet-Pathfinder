---
title: PathfinderAPI/SteamPatches.cs

---

# PathfinderAPI/SteamPatches.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::SteamPatches](../Classes/class_pathfinder_1_1_steam_patches/)**  |




## Source code

```csharp
using System.Reflection;
using Hacknet;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;
using Pathfinder.Options;

namespace Pathfinder;

[HarmonyPatch]
public class SteamPatches
{
    [HarmonyPrepare]
    internal static bool Prepare(MethodBase original) =>
        PathfinderAPIPlugin.GameIsSteamVersion;

    [HarmonyILManipulator]
    [HarmonyPatch(typeof(PlatformAPISettings), nameof(PlatformAPISettings.InitPlatformAPI))]
    private static void NoSteamCloudSavesIL(ILContext il)
    {
        ILCursor c = new ILCursor(il);
            
        c.GotoNext(MoveType.Before, x => x.MatchStsfld(AccessTools.Field(typeof(PlatformAPISettings), nameof(PlatformAPISettings.RemoteStorageRunning))));

        c.Emit(OpCodes.Pop);
        c.Emit(OpCodes.Ldc_I4_0);
    }

    [HarmonyILManipulator]
    [HarmonyPatch(typeof(MainMenu), nameof(MainMenu.drawMainMenuButtons))]
    private static void NoSteamErrorMessageIL(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        c.GotoNext(MoveType.Before, x => x.MatchLdsfld(AccessTools.Field(typeof(PlatformAPISettings), nameof(PlatformAPISettings.RemoteStorageRunning))));

        c.RemoveRange(3);

        c.Emit(OpCodes.Ldsfld, AccessTools.Field(typeof(PathfinderOptions), nameof(PathfinderOptions.DisableSteamCloudError)));
        c.Emit(OpCodes.Ldfld, AccessTools.Field(typeof(OptionCheckbox), nameof(OptionCheckbox.Value)));

        c.GotoNext(MoveType.Before, x => x.MatchLdstr(out _));
        c.Next.Operand = "Steam Cloud saving disabled by Pathfinder";
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
