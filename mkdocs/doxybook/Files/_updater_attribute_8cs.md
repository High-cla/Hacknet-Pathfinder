---
title: PathfinderAPI/Meta/UpdaterAttribute.cs

---

# PathfinderAPI/Meta/UpdaterAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::UpdaterAttribute](../Classes/class_pathfinder_1_1_meta_1_1_updater_attribute/)**  |




## Source code

```csharp
namespace Pathfinder.Meta;

public class UpdaterAttribute : Attribute
{
    public string GithubApiUrl { get; set; }
    public string AssetFileName { get; set; }
    public string ZipEntryPath { get; set; }
    public bool IncludePrerelease { get; set; }

    public UpdaterAttribute(string apiUrl, string assetName, string zipPath = null, bool includePrerlease = false)
    {
        GithubApiUrl = apiUrl;
        AssetFileName = assetName;
        ZipEntryPath = zipPath;
        IncludePrerelease = includePrerlease;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
