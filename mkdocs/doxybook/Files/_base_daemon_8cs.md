---
title: PathfinderAPI/Daemon/BaseDaemon.cs

---

# PathfinderAPI/Daemon/BaseDaemon.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Daemon](../Namespaces/namespace_pathfinder_1_1_daemon/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Daemon::BaseDaemon](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;
using Pathfinder.Util;
using Pathfinder.Util.XML;

namespace Pathfinder.Daemon;

public abstract class BaseDaemon : Hacknet.Daemon
{
    public BaseDaemon(Computer computer, string serviceName, OS opSystem) : base(computer, serviceName, opSystem)
    {
        this.name = Identifier;
    }

    public virtual string Identifier => this.GetType().Name;

    public sealed override string getSaveString() => null;

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
