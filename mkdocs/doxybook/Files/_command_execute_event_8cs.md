---
title: PathfinderAPI/Event/Gameplay/CommandExecuteEvent.cs

---

# PathfinderAPI/Event/Gameplay/CommandExecuteEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Gameplay](../Namespaces/namespace_pathfinder_1_1_event_1_1_gameplay/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Gameplay::CommandExecuteEvent](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_command_execute_event/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;

namespace Pathfinder.Event.Gameplay;

[HarmonyPatch]
public class CommandExecuteEvent : PathfinderEvent
{
    public OS Os { get; }
    public string[] Args { get; set; }
    private bool found = false;
    public bool Found
    {
        get => found;
        set => found |= value;
    }

    public CommandExecuteEvent(OS os, string[] args)
    {
        Os = os;
        Args = args;
    }

    [HarmonyPrefix]
    [HarmonyPatch(typeof(ProgramRunner), nameof(ProgramRunner.ExecuteProgram))]
    private static bool OnCommandExecutePrefix(ref object os_object, ref string[] arguments, ref bool __result)
    {
        var commandExecuteEvent = new CommandExecuteEvent((OS)os_object, arguments);
        EventManager<CommandExecuteEvent>.InvokeAll(commandExecuteEvent);

        arguments = commandExecuteEvent.Args;
        __result = commandExecuteEvent.Found;
        return !commandExecuteEvent.Cancelled;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
