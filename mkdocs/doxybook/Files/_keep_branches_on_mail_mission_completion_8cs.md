---
title: PathfinderAPI/BaseGameFixes/KeepBranchesOnMailMissionCompletion.cs

---

# PathfinderAPI/BaseGameFixes/KeepBranchesOnMailMissionCompletion.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |
| **[MonoMod::Utils](../Namespaces/namespace_mono_mod_1_1_utils/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::BaseGameFixes::KeepBranchesOnMailMissionCompletion](../Classes/class_pathfinder_1_1_base_game_fixes_1_1_keep_branches_on_mail_mission_completion/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Mono.Cecil;
using Mono.Cecil.Cil;
using MonoMod.Cil;
using MonoMod.Utils;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
public static class KeepBranchesOnMailMissionCompletion {
    [HarmonyPatch(typeof(MailServer), nameof(MailServer.doRespondDisplay))]
    [HarmonyILManipulator]
    public static void DoRespondDisplayManipulator(ILContext context) {
        ILCursor cursor = new(context);

        cursor.GotoNext(MoveType.After,
            x => x.MatchLdarg(0),
            x => x.MatchLdarg(0),
            x => x.MatchLdfld<Hacknet.Daemon>("os"),
            x => x.MatchLdfld<OS>("branchMissions"),
            x => x.MatchLdloc(4),
            x => x.MatchCallvirt(out MethodReference method) &&
                method.DeclaringType.Is(typeof(List<ActiveMission>)) &&
                method.Name == "get_Item"
            ,
            x => x.MatchCall<MailServer>("attemptCompleteMission"),
            x => x.MatchStloc(11)
        );
        Instruction startOfRange = cursor.Next;

        cursor.GotoNext(MoveType.After,
            x => x.MatchLdarg(0),
            x => x.MatchLdfld<Hacknet.Daemon>("os"),
            x => x.MatchLdfld<OS>("branchMissions"),
            x => x.MatchCallvirt(out MethodReference method) &&
                method.DeclaringType.Is(typeof(List<ActiveMission>)) &&
                method.Name == "Clear"
        );
        Instruction endOfRange = cursor.Prev;

        cursor.Goto(startOfRange);
        int count = cursor.Instrs.IndexOf(endOfRange) - cursor.Instrs.IndexOf(startOfRange) + 1;
        cursor.RemoveRange(count);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
