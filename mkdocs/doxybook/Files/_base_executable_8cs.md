---
title: PathfinderAPI/Executable/BaseExecutable.cs

---

# PathfinderAPI/Executable/BaseExecutable.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Executable](../Namespaces/namespace_pathfinder_1_1_executable/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Executable::BaseExecutable](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/)**  |




## Source code

```csharp
using Hacknet;
using Microsoft.Xna.Framework;

namespace Pathfinder.Executable;

public abstract class BaseExecutable : ExeModule
{
    [Obsolete("To be removed in 6.0.0")]
    public virtual string GetIdentifier() => null;

    public string[] Args;

    public BaseExecutable(Rectangle location, OS operatingSystem, string[] args) : base(location, operatingSystem)
    {
        Args = args;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
