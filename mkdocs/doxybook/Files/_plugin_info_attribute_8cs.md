---
title: PathfinderAPI/Meta/PluginInfoAttribute.cs

---

# PathfinderAPI/Meta/PluginInfoAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::PluginInfoAttribute](../Classes/class_pathfinder_1_1_meta_1_1_plugin_info_attribute/)**  |




## Source code

```csharp
namespace Pathfinder.Meta;

public class PluginInfoAttribute : System.Attribute
{
    public string Description;
    public string ImageName;
    public string[] Authors;
    public string TeamName;

    public PluginInfoAttribute(string description, string teamName = null, string author = null)
    {
        Description = description;
        if(author != null) Authors = new []{ author };
        TeamName = teamName;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
