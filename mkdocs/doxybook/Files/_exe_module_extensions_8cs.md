---
title: PathfinderAPI/Executable/ExeModuleExtensions.cs

---

# PathfinderAPI/Executable/ExeModuleExtensions.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Executable](../Namespaces/namespace_pathfinder_1_1_executable/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Executable::ExeModuleExtensions](../Classes/class_pathfinder_1_1_executable_1_1_exe_module_extensions/)**  |




## Source code

```csharp
using Hacknet;

namespace Pathfinder.Executable;

public static class ExeModuleExtensions
{
    public static bool CanKill(this ExeModule module) =>
        !(
            !module.os.exes.Contains(module) ||
            ((module is GameExecutable gameExe) && !gameExe.CanBeKilled) ||
            ((module is DLCIntroExe introExe) && !((introExe.State == DLCIntroExe.IntroState.NotStarted) || (introExe.State == DLCIntroExe.IntroState.Exiting))) ||
            ((module is ExtensionSequencerExe seqExe) && (seqExe.state == ExtensionSequencerExe.SequencerExeState.Active))
        );

    public static bool Kill(this ExeModule module)
    {
        if(!module.CanKill())
            return false;
        module.Killed();
        return module.os.exes.Remove(module);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
