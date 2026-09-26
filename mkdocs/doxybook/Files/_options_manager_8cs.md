---
title: PathfinderAPI/Options/OptionsManager.cs

---

# PathfinderAPI/Options/OptionsManager.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Options](../Namespaces/namespace_pathfinder_1_1_options/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Options::OptionsManager](../Classes/class_pathfinder_1_1_options_1_1_options_manager/)**  |
| class | **[Pathfinder::Options::OptionsTab](../Classes/class_pathfinder_1_1_options_1_1_options_tab/)**  |




## Source code

```csharp
using Pathfinder.GUI;

namespace Pathfinder.Options;

public static class OptionsManager
{
    public readonly static Dictionary<string, OptionsTab> Tabs = new Dictionary<string, OptionsTab>();

    static OptionsManager() { }

    public static void AddOption(string tag, Option opt)
    {
        if (!Tabs.TryGetValue(tag, out var tab)) {
            tab = new OptionsTab(tag);
            Tabs.Add(tag, tab);
        }
        tab.Options.Add(opt);
    }
}

public class OptionsTab
{
    public string Name;

    public List<Option> Options = new List<Option>();

    internal int ButtonID = PFButton.GetNextID();

    public OptionsTab(string name) {
        Name = name;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
