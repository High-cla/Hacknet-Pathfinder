---
title: PathfinderAPI/Logger.cs

---

# PathfinderAPI/Logger.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |




## Source code

```csharp
using BepInEx.Logging;

namespace Pathfinder;

internal static class Logger
{
    internal static ManualLogSource LogSource;

    internal static void Log(LogLevel severity, object msg) => LogSource.Log(severity, msg); 
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
