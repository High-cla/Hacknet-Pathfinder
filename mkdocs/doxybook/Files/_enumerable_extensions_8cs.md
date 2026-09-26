---
title: PathfinderAPI/Util/EnumerableExtensions.cs

---

# PathfinderAPI/Util/EnumerableExtensions.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Util](../Namespaces/namespace_pathfinder_1_1_util/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::EnumerableExtensions](../Classes/class_pathfinder_1_1_util_1_1_enumerable_extensions/)**  |




## Source code

```csharp

namespace Pathfinder.Util;

public static class EnumerableExtensions
{
    public static T? FirstOrNull<T>(this IEnumerable<T> source) where T : struct {
        using IEnumerator<T> iter = source.GetEnumerator();
        if(iter.MoveNext())
            return iter.Current;
        return null;
    }

    public static T? FirstOrNull<T>(this IEnumerable<T> source, Func<T, bool> predicate) where T : struct {
        foreach(T item in source) {
            if(predicate(item))
                return item;
        }
        return null;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
