---
title: PathfinderAPI/Meta/Load/PortAttribute.cs

---

# PathfinderAPI/Meta/Load/PortAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::PortAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_port_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Pathfinder.Port;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]
public class PortAttribute : BaseAttribute
{
    public PortAttribute()
    {
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        if(targettedInfo.DeclaringType != plugin.GetType())
            throw new InvalidOperationException($"Pathfinder.Meta.Load.PortAttribute is only valid in a class derived from BepInEx.Hacknet.HacknetPlugin");

        object portRecord = null;
        switch(targettedInfo)
        {
            case PropertyInfo propertyInfo:
                if(propertyInfo.PropertyType != typeof(PortRecord))
                    throw new InvalidOperationException($"Property {propertyInfo.Name}'s type does not derive from Pathfinder.Port.PortRecord");
                portRecord = propertyInfo.GetGetMethod()?.Invoke(plugin, null);
                break;
            case FieldInfo fieldInfo:
                if(fieldInfo.FieldType != typeof(PortRecord))
                    throw new InvalidOperationException($"Field {fieldInfo.Name}'s type does not derive from Pathfinder.Port.PortRecord");
                portRecord = fieldInfo.GetValue(plugin);
                break;
        }

        if(portRecord == null)
            throw new InvalidOperationException($"PortRecord not set to a default value, PortRecord should be set before HacknetPlugin.Load() is called");

        PortManager.RegisterPortInternal((PortRecord)portRecord, targettedInfo.Module.Assembly);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
