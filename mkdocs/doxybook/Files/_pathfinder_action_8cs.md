---
title: PathfinderAPI/Action/PathfinderAction.cs

---

# PathfinderAPI/Action/PathfinderAction.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Action](../Namespaces/namespace_pathfinder_1_1_action/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Action::PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;
using Pathfinder.Util;
using Pathfinder.Util.XML;

namespace Pathfinder.Action;

public abstract class PathfinderAction : SerializableAction, IXmlName
{

    public string XmlName => ActionManager.GetXmlNameFor(this.GetType()) ?? this.GetType().Name;
        
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

Updated on 2026-09-26 at 01:20:08 +0000
