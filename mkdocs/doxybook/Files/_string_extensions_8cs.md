---
title: PathfinderAPI/Util/StringExtensions.cs

---

# PathfinderAPI/Util/StringExtensions.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Util](../Namespaces/namespace_pathfinder_1_1_util/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::StringExtensions](../Classes/class_pathfinder_1_1_util_1_1_string_extensions/)**  |




## Source code

```csharp
using Hacknet;
using Hacknet.Extensions;

namespace Pathfinder.Util;

public static class StringExtensions
{
    public static bool HasContent(this string s) => !string.IsNullOrWhiteSpace(s);

    public static bool ContentFileExists(this string filename) => File.Exists(filename.ContentFilePath());

    public static string ContentFilePath(this string filename)
    {
        filename = filename.Replace("\\", "/");
        if (Settings.IsInExtensionMode)
        {
            var extFolder = ExtensionLoader.ActiveExtensionInfo.FolderPath.Replace("\\", "/");
            return filename.StartsWith(extFolder) ? filename : Path.Combine(extFolder, filename);
        }
        return filename.StartsWith("Content/") ? filename : Path.Combine("Content", filename);
    }

    public static string Filter(this string s) => s == null ? null : ComputerLoader.filter(s);
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
