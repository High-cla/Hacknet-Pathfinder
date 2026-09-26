---
title: PathfinderAPI/Action/DelayablePathfinderAction.cs

---

# PathfinderAPI/Action/DelayablePathfinderAction.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Action](../Namespaces/namespace_pathfinder_1_1_action/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Action::DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/)**  |




## Source code

```csharp
using Hacknet;
using Pathfinder.Util;
using Pathfinder.Util.XML;

namespace Pathfinder.Action;

public abstract class DelayablePathfinderAction : PathfinderAction
{
    [XMLStorage]
    public string DelayHost; 
    [XMLStorage]
    public string Delay;

    private DelayableActionSystem delayHost;
    private float delay = 0f;
        
    public sealed override void Trigger(object os_obj)
    {
        if (delayHost == null && DelayHost != null)
        {
            var delayComp = Programs.getComputer(OS.currentInstance, DelayHost);
            if (delayComp == null)
                throw new FormatException($"{this.GetType().Name}: DelayHost could not be found");
            delayHost = DelayableActionSystem.FindDelayableActionSystemOnComputer(delayComp);
        }
            
        if (delay <= 0f || delayHost == null)
        {
            Trigger((OS)os_obj);
            return;
        }

        DelayHost = null;
        Delay = null;
        delayHost.AddAction(this, delay);
        delay = 0f;
    }

    public abstract void Trigger(OS os);

    public override void LoadFromXml(ElementInfo info)
    {
        base.LoadFromXml(info);
            
        if (Delay != null && !float.TryParse(Delay, out delay))
            throw new FormatException($"{this.GetType().Name}: Couldn't parse delay time!");
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
