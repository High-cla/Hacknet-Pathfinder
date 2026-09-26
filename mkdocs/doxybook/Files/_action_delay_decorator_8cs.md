---
title: PathfinderAPI/Action/ActionDelayDecorator.cs

---

# PathfinderAPI/Action/ActionDelayDecorator.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Action](../Namespaces/namespace_pathfinder_1_1_action/)**  |
| **[System::Xml::Linq](../Namespaces/namespace_system_1_1_xml_1_1_linq/)**  |
| **[Hacknet](../Namespaces/namespace_hacknet/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Action::ActionDelayDecorator](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/)**  |




## Source code

```csharp
using System.Xml.Linq;
using Hacknet;
using Pathfinder.Replacements;
using Pathfinder.Util.XML;

namespace Pathfinder.Action;

public sealed class ActionDelayDecorator : DelayablePathfinderAction
{
    public static SerializableAction Create(ElementInfo info, SerializableAction action)
    {
        if (info.Attributes.ContainsKey("Delay") && info.Attributes.ContainsKey("DelayHost"))
            return new ActionDelayDecorator(info, action);

        return action;
    }

    SerializableAction targetAction;

    public ActionDelayDecorator(ElementInfo info, SerializableAction action)
    {
        LoadFromXml(info);
        targetAction = action;
    }

    public override void Trigger(OS os)
    {
        targetAction.Trigger(os);
    }

    public override XElement GetSaveElement()
    {
        XElement element = SaveWriter.GetActionSaveElement(targetAction);
        element.SetAttributeValue("Delay", Delay);
        element.SetAttributeValue("DelayHost", DelayHost);
        return element;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
