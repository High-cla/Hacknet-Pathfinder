---
title: PathfinderAPI/Action/ConditionManager.cs

---

# PathfinderAPI/Action/ConditionManager.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Action](../Namespaces/namespace_pathfinder_1_1_action/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Action::ConditionManager](../Classes/class_pathfinder_1_1_action_1_1_condition_manager/)**  |




## Source code

```csharp
using System.Reflection;
using System.Text;
using System.Xml;
using Hacknet;
using HarmonyLib;
using Pathfinder.Event;
using Pathfinder.Util.XML;
using Pathfinder.Util;

namespace Pathfinder.Action;

[HarmonyPatch]
public static class ConditionManager
{
    private static readonly Dictionary<string, Type> CustomConditions = new Dictionary<string, Type>();
    private static readonly Dictionary<Type, string> XmlNames = new Dictionary<Type, string>();

    static ConditionManager()
    {
        EventManager.onPluginUnload += OnPluginUnload;
    }
        
    internal static bool TryLoadCustomCondition(ElementInfo info, out PathfinderCondition action)
    {
        if (CustomConditions.TryGetValue(info.Name, out var actionType))
        {
            action = (PathfinderCondition)Activator.CreateInstance(actionType);
            action.LoadFromXml(info);
            return true;
        }

        action = null;
        return false;
    }
        
    private static void OnPluginUnload(Assembly pluginAsm)
    {
        foreach (var entry in CustomConditions.Where(x => x.Value.Assembly == pluginAsm).ToList())
        {
            CustomConditions.Remove(entry.Key);
            XmlNames.Remove(entry.Value);
        }
    }
        
    public static void RegisterCondition<T>(string xmlName) where T : PathfinderCondition => RegisterCondition(typeof(T), xmlName);
    public static void RegisterCondition(Type conditionType, string xmlName)
    {
        conditionType.ThrowNotInherit<PathfinderCondition>(nameof(conditionType));
        CustomConditions.Add(xmlName, conditionType);
        if (!XmlNames.ContainsKey(conditionType))
            XmlNames.Add(conditionType, xmlName);
    }

    public static void UnregisterCondition<T>() where T : PathfinderCondition => UnregisterCondition(typeof(T));
    public static void UnregisterCondition(Type conditionType)
    {
        foreach(var xmlName in CustomConditions.Where(x => x.Value == conditionType).Select(x => x.Key).ToList())
            CustomConditions.Remove(xmlName);
        if(XmlNames.ContainsKey(conditionType))
            XmlNames.Remove(conditionType);
    }
    public static void UnregisterCondition(string xmlName)
    {
        if (!CustomConditions.ContainsKey(xmlName))
            return;
        var conditionType = CustomConditions[xmlName];
        CustomConditions.Remove(xmlName);
        if (XmlNames[conditionType] != xmlName)
            return;
        /* find the next applicable name */
        string nextName = CustomConditions.FirstOrDefault(x => x.Value == conditionType).Key;
        if (nextName == null)
            XmlNames.Remove(conditionType);
        else
            XmlNames[conditionType] = nextName;
    }
    public static string GetXmlNameFor(Type type)
    {
        XmlNames.TryGetValue(type, out string retVal);
        return retVal;
    }
        
    [HarmonyPrefix]
    [HarmonyPatch(typeof(SerializableCondition), nameof(SerializableCondition.GetSaveString))]
    internal static bool GetSaveStringOverridePrefix(SerializableCondition __instance, ref string __result)
    {
        if (__instance is PathfinderCondition pfCondition)
        {
            var builder = new StringBuilder();
            using (var writer = XmlWriter.Create(builder))
                pfCondition.GetSaveElement().WriteTo(writer);
            __result = builder.ToString();
            return false;
        }

        return true;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
