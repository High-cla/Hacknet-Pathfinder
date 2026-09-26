---
title: PathfinderAPI/Administrator/BaseAdministrator.cs

---

# PathfinderAPI/Administrator/BaseAdministrator.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Administrator](../Namespaces/namespace_pathfinder_1_1_administrator/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Administrator::BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;
using Pathfinder.Util;
using Pathfinder.Util.XML;

namespace Pathfinder.Administrator;

public abstract class BaseAdministrator : Hacknet.Administrator, IXmlName
{
    protected Computer computer;
    protected OS opSystem;

    public BaseAdministrator(Computer computer, OS opSystem) : base()
    {
        this.computer = computer;
        this.opSystem = opSystem;
    }
    
    public string XmlName => "admin";
        
    public virtual void LoadFromXml(ElementInfo info)
    {
        base.ResetsPassword = info.Attributes.GetBool("resetPass");
        base.IsSuper = info.Attributes.GetBool("isSuper");
            
        XMLStorageAttribute.ReadFromElement(info, this);
    }

    public virtual XElement GetSaveElement()
    {
        return XMLStorageAttribute.WriteToElement(this);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
