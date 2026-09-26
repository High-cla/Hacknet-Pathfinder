---
title: PathfinderAPI/Meta/Load/AttributeManager.cs

---

# PathfinderAPI/Meta/Load/AttributeManager.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.Meta.Load;

[HarmonyPatch]
internal static class AttributeManager
{
    [HarmonyILManipulator]
    [HarmonyPatch(typeof(HacknetChainloader), nameof(HacknetChainloader.LoadPlugin))]
    private static void OnPluginLoadIL(ILContext il)
    {
        var c = new ILCursor(il);

        c.GotoNext(
            x => x.MatchCallvirt(AccessTools.Method(typeof(HacknetPlugin), nameof(HacknetPlugin.Load)))
        );

        c.Emit(OpCodes.Dup);
        c.Emit(OpCodes.Call, AccessTools.Method(typeof(AttributeManager), nameof(ReadAttributesFor)));
    }

    public static void ReadAttributesFor(HacknetPlugin plugin)
    {
        var pluginType = plugin.GetType();
        if(pluginType.GetCustomAttribute<IgnorePluginAttribute>() != null)
            return;
        ReadAttributesOnType(plugin, pluginType);
        foreach(var type in pluginType.Assembly.GetTypes())
        {
            if(type == pluginType) continue;
            ReadAttributesOnType(plugin, type);
        }
    }

    private static void ReadAttributesOnType(HacknetPlugin plugin, Type type)
    {
        foreach (var attribute in type.GetCustomAttributes<BaseAttribute>())
        {
            attribute.CallOn(plugin, type);
        }
        foreach (var member in type.GetMembers(BindingFlags.Public | BindingFlags.NonPublic | BindingFlags.Instance | BindingFlags.Static))
        {
            if (member.MemberType == MemberTypes.NestedType)
            {
                ReadAttributesOnType(plugin, (Type)member);
            }
            else foreach (var attribute in member.GetCustomAttributes<BaseAttribute>())
            {
                attribute.CallOn(plugin, member);
            }
        }
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
