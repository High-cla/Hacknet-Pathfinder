---
title: PathfinderAPI/BaseGameFixes/SendEmailMission.cs

---

# PathfinderAPI/BaseGameFixes/SendEmailMission.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::BaseGameFixes](../Namespaces/namespace_pathfinder_1_1_base_game_fixes/)**  |




## Source code

```csharp
using HarmonyLib;
using MonoMod.Cil;
using Hacknet;

namespace Pathfinder.BaseGameFixes;

[HarmonyPatch]
internal static class SendEmailMission
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(MailServer), nameof(MailServer.MailWithSubjectExists))]
    public static void IndexIntoInboxFolderIL(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        c.GotoNext(MoveType.Before,
            x => x.MatchStloc(1)
        );

        c.EmitDelegate<Func<Folder, Folder>>(folder => folder.folders[0]);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
