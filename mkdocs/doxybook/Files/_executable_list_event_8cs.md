---
title: PathfinderAPI/Event/Gameplay/ExecutableListEvent.cs

---

# PathfinderAPI/Event/Gameplay/ExecutableListEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Gameplay](../Namespaces/namespace_pathfinder_1_1_event_1_1_gameplay/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Gameplay::ExecutableListEvent](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_list_event/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;

namespace Pathfinder.Event.Gameplay;

[HarmonyPatch]
public class ExecutableListEvent : PathfinderEvent
{
    public OS OS { get; }

    public List<string> EmbeddedExes { get; } = new List<string>
    {
        "PortHack", "ForkBomb", "Shell", "Tutorial"
    };
    public Dictionary<FileEntry, bool> BinExes { get; }

    public ExecutableListEvent(OS os, Dictionary<FileEntry, bool> binExes)
    {
        OS = os;
        BinExes = binExes;
    }

    [HarmonyPrefix]
    [HarmonyPatch(typeof(Programs), nameof(Programs.execute))]
    private static bool ProgramsExecuteReplacement(string[] args, OS os){
        var binFiles = os.thisComputer.files.root.searchForFolder("bin").files; // folders[2].files;

        var binExes = new Dictionary<FileEntry, bool>();
        foreach (FileEntry exeFile in binFiles)
            binExes[exeFile] =
                PortExploits.crackExeData        .Any(x => x.Value == exeFile.data) ||
                PortExploits.crackExeDataLocalRNG.Any(x => x.Value == exeFile.data);

        var programsExecute = new ExecutableListEvent(os, binExes);
        EventManager<ExecutableListEvent>.InvokeAll(programsExecute);

        os.write("Available Executables:\n");
        
        foreach (string embedded in programsExecute.EmbeddedExes)
            os.write(embedded);
        foreach (FileEntry file in binFiles.Where(x => binExes[x]))
            os.write(file.name.Replace(".exe", ""));

        os.write(" ");
        return false;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
