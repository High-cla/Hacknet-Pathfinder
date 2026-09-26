---
title: PathfinderAPI/Mission/GoalManager.cs

---

# PathfinderAPI/Mission/GoalManager.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Mission](../Namespaces/namespace_pathfinder_1_1_mission/)**  |
| **[Hacknet::Mission](../Namespaces/namespace_hacknet_1_1_mission/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Mission::GoalManager](../Classes/class_pathfinder_1_1_mission_1_1_goal_manager/)**  |




## Source code

```csharp
using System.Reflection;
using Hacknet.Mission;
using Pathfinder.Event;
using Pathfinder.Util;

namespace Pathfinder.Mission;

public static class GoalManager
{
    private static readonly Dictionary<string, Type> CustomGoals = new Dictionary<string, Type>();

    static GoalManager()
    {
        EventManager.onPluginUnload += OnPluginUnload;
    }

    internal static bool TryLoadCustomGoal(string type, out MisisonGoal customGoal)
    {
        if (CustomGoals.TryGetValue(type, out var goalType))
        {
            customGoal = (MisisonGoal)Activator.CreateInstance(goalType);
            return true;
        }

        customGoal = null;
        return false;
    }

    private static void OnPluginUnload(Assembly pluginAsm)
    {
        foreach (var name in CustomGoals.Where(x => x.Value.Assembly == pluginAsm).Select(x => x.Key).ToList())
            CustomGoals.Remove(name);
    }
        
    public static void RegisterGoal<T>(string xmlName) where T : MisisonGoal => RegisterGoal(typeof(T), xmlName);
    public static void RegisterGoal(Type goalType, string xmlName)
    {
        goalType.ThrowNotInherit<MisisonGoal>(nameof(goalType), " (yes, that is how it's spelled)");
        CustomGoals.Add(xmlName.ToLower(), goalType);
    }

    public static void UnregisterGoal<T>() => UnregisterGoal(typeof(T));
    public static void UnregisterGoal(Type goalType)
    {
        var xmlName = CustomGoals.FirstOrDefault(x => x.Value == goalType).Key;
        if (xmlName != null)
            CustomGoals.Remove(xmlName);
    }
    public static void UnregisterGoal(string xmlName)
    {
        CustomGoals.Remove(xmlName.ToLower());
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
