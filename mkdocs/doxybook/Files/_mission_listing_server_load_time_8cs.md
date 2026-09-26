---
title: PathfinderAPI/BaseGameFixes/MissionListingServerLoadTime.cs

---

# PathfinderAPI/BaseGameFixes/MissionListingServerLoadTime.cs



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
using Pathfinder.Replacements;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal static class MissionListingServerLoadTime
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(MissionListingServer), nameof(MissionListingServer.addListingsForGroup))]
    internal static void FixMissionLoadTimes(ILContext il)
    {
        ILCursor c = new ILCursor(il);
            
        c.GotoNext(MoveType.Before, 
            x => x.MatchLdarg(0),
            x => x.MatchLdfld(AccessTools.Field(typeof(MissionListingServer), nameof(MissionListingServer.CustomFolderLoadPath)))
        );

        c.Index += 1;
        var start = c.MarkLabel();
            
        c.GotoNext(MoveType.Before,
            x => x.MatchNop(),
            x => x.MatchNop(),
            x => x.MatchBr(out _),
            x => x.MatchLdarg(0),
            x => x.MatchLdfld(AccessTools.Field(typeof(MissionListingServer), nameof(MissionListingServer.groupName)))
        );

        var end = c.Index;

        c.GotoLabel(start);

        c.RemoveRange(end - c.Index);

        c.Emit(OpCodes.Ldloc_1);
        c.EmitDelegate<Action<MissionListingServer, bool>>((listingDaemon, shouldGen) =>
        {
            ComputerLoader.postAllLoadedActions += () =>
            {
                foreach (var file in Directory.GetFiles(listingDaemon.CustomFolderLoadPath, "*.xml"))
                {
                    OS.currentInstance.branchMissions = new List<ActiveMission>();
                    listingDaemon.addMisison(MissionLoader.LoadContentMission(file));
                }

                if (shouldGen)
                {
                    for (int i = 0; i < 2; i++)
                    {
                        OS.currentInstance.branchMissions = new List<ActiveMission>();
                        listingDaemon.addMisison((ActiveMission)MissionGenerator.generate(2));
                    }
                }
            };
        });
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
