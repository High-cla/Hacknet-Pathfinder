---
title: PathfinderAPI/Meta/Load/BaseAttribute.cs

---

# PathfinderAPI/Meta/Load/BaseAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::BaseAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_base_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;

namespace Pathfinder.Meta.Load;

public abstract class BaseAttribute : Attribute
{
    internal protected abstract void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo);

    internal void ThrowOnInvalidOperation(bool evaluation, string message)
    {
        if(evaluation)
            throw new InvalidOperationException(message);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
