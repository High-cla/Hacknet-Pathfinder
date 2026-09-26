---
title: PathfinderAPI/Meta/PluginWebsiteAttribute.cs

---

# PathfinderAPI/Meta/PluginWebsiteAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::PluginWebsiteAttribute](../Classes/class_pathfinder_1_1_meta_1_1_plugin_website_attribute/)**  |




## Source code

```csharp
namespace Pathfinder.Meta;

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]
public class PluginWebsiteAttribute : System.Attribute
{
    public string WebsiteName;
    public string WebsiteUrl;

    public PluginWebsiteAttribute(string websiteName, string websiteUrl)
    {
        WebsiteName = websiteName;
        WebsiteUrl = websiteUrl;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
