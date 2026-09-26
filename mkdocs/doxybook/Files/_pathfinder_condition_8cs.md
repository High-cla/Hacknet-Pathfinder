---
title: PathfinderAPI/Action/PathfinderCondition.cs

---

# PathfinderAPI/Action/PathfinderCondition.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Action](../Namespaces/namespace_pathfinder_1_1_action/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Action::PathfinderCondition](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_condition/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;
using Pathfinder.Util;
using Pathfinder.Util.XML;

namespace Pathfinder.Action;

public abstract class PathfinderCondition : SerializableCondition, IXmlName
{
    public string XmlName => ConditionManager.GetXmlNameFor(this.GetType()) ?? this.GetType().Name;
        
    public virtual XElement GetSaveElement()
    {
        return XMLStorageAttribute.WriteToElement(this);
    }

    public virtual void LoadFromXml(ElementInfo info)
    {
        XMLStorageAttribute.ReadFromElement(info, this);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
