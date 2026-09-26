---
title: PathfinderAPI/Util/ErrorHelper.cs

---

# PathfinderAPI/Util/ErrorHelper.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Util](../Namespaces/namespace_pathfinder_1_1_util/)**  |
| **[System::Collections](../Namespaces/namespace_system_1_1_collections/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::ErrorHelper](../Classes/class_pathfinder_1_1_util_1_1_error_helper/)**  |




## Source code

```csharp
using System.Collections;

namespace Pathfinder.Util;

public static class ErrorHelper
{
    public static void ThrowNotInherit(this Type type, string typeRefName, Type parentType, string extra = null)
    {
        if(!parentType.IsAssignableFrom(type))
            throw new ArgumentException($"{typeRefName} type must inherit from {parentType.FullName}!{extra}", typeRefName);
    }

    public static void ThrowNotInherit<InheritT>(this Type type, string typeRefName, string extra = null)
        => type.ThrowNotInherit(typeRefName, typeof(InheritT), extra);

    public static void ThrowNoDefaultCtor(this Type type, string nameOf)
    {
        if(type.GetConstructors().All(m => m.GetParameters().Length != 0))
            throw new ArgumentException($"{nameOf} must have a default constructor", nameOf);
    }

    public static void ThrowNull<T>(this T check, string nameOf) where T : class
    {
        if(check == null)
            throw new ArgumentNullException(nameOf);
    }

    public static void ThrowNull<T>(this T check, string nameOf, string msg) where T : class
    {
        if(check == null)
            throw new ArgumentNullException(nameOf, msg);
    }

    public static void ThrowOutOfRange(this int check, string nameOf, int lowerLimit = int.MinValue, int upperLimit = int.MaxValue)
    {
        if(check < lowerLimit || check > upperLimit)
            throw new ArgumentOutOfRangeException(nameOf);
    }

    public static void ThrowNotSameSizeAs(this ICollection left, string leftNameOf, ICollection right, string rightNameOf)
    {
        if(left.Count != right.Count)
            throw new ArgumentException($"{leftNameOf} is not same size as {rightNameOf}");
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
