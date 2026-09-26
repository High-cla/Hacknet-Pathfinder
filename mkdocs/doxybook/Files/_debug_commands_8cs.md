---
title: PathfinderAPI/Command/DebugCommands.cs

---

# PathfinderAPI/Command/DebugCommands.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Command](../Namespaces/namespace_pathfinder_1_1_command/)**  |




## Source code

```csharp
using Hacknet;
using Pathfinder.Util;

namespace Pathfinder.Command;

internal static class DebugCommands
{
    internal static void AddCommands()
    {
        CommandManager.RegisterCommand("loadmission", LoadMission);
        CommandManager.RegisterCommand("loadactions", LoadActions);
        CommandManager.RegisterCommand("dscan", DScanReplacement);
    }

    private static void LoadMission(OS os, string[] args)
    {
        os.currentMission = Replacements.MissionLoader.LoadContentMission(string.Join(" ", args.Skip(1)).ContentFilePath());
        os.currentMission.sendEmail(os);
    }

    private static void LoadActions(OS os, string[] args)
    {
        RunnableConditionalActions.LoadIntoOS(string.Join(" ", args.Skip(1)), os);
    }

    private static void DScanReplacement(OS os, string[] args)
    {
        if (args.Length < 2)
        {
            os.write("No Node ID Given");
            return;
        }
        var comp = ComputerLookup.FindById(args[1]);
        if (comp != null)
        {
            os.netMap.discoverNode(comp);
            comp.highlightFlashTime = 1f;
        }
        else
        {
            os.write("Node ID Not found");
        }
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
