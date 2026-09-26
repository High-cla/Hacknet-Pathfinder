---
title: PathfinderAPI/Meta/Load/OptionAttribute.cs

---

# PathfinderAPI/Meta/Load/OptionAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::OptionAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_option_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Options;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]
public class OptionAttribute : BaseAttribute
{
    public string Tag { get; set; }

    public OptionAttribute(string tag = null)
    {
        this.Tag = tag;
    }

    public OptionAttribute(Type pluginType)
    {
        this.Tag = pluginType.GetCustomAttribute<OptionsTabAttribute>()?.Tag;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        if(Tag == null)
        {
            Tag = plugin.GetOptionsTag();
            if(Tag == null)
                throw new InvalidOperationException($"Could not find Pathfinder.Meta.Load.OptionsTabAttribute for {targettedInfo.DeclaringType.FullName}");
        }

        if(targettedInfo.DeclaringType != plugin.GetType())
            throw new InvalidOperationException($"Pathfinder.Meta.Load.OptionAttribute is only valid in a class derived from BepInEx.Hacknet.HacknetPlugin");

        Option option = null;
        switch(targettedInfo)
        {
            case PropertyInfo propertyInfo:
                if(!propertyInfo.PropertyType.IsSubclassOf(typeof(Option)))
                    throw new InvalidOperationException($"Property {propertyInfo.Name}'s type does not derive from Pathfinder.Options.Option");
                option = (Option)(propertyInfo.GetGetMethod()?.Invoke(plugin, null));
                break;
            case FieldInfo fieldInfo:
                if(!fieldInfo.FieldType.IsSubclassOf(typeof(Option)))
                    throw new InvalidOperationException($"Field {fieldInfo.Name}'s type does not derive from Pathfinder.Options.Option");
                option = (Option)fieldInfo.GetValue(plugin);
                break;
        }

        if(option == null)
            throw new InvalidOperationException($"Option not set to a default value, Option members should be set before HacknetPlugin.Load() is called");

        OptionsManager.AddOption(Tag, option);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
