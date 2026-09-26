---
title: Pathfinder::Action::ActionDelayDecorator

---

# Pathfinder::Action::ActionDelayDecorator





Inherits from [Pathfinder.Action.DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/), [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/), SerializableAction, [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| SerializableAction | **[Create](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/#function-create)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info, SerializableAction action) |
| | **[ActionDelayDecorator](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/#function-actiondelaydecorator)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info, SerializableAction action) |
| override void | **[Trigger](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/#function-trigger)**(OS os) |
| virtual override XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/#function-getsaveelement)**() |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Action.DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| virtual override void | **[LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

**Public Attributes inherited from [Pathfinder.Action.DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| string | **[DelayHost](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#variable-delayhost)**  |
| string | **[Delay](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#variable-delay)**  |

**Public Functions inherited from [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| virtual void | **[LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

**Public Properties inherited from [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#property-xmlname)**  |

**Public Properties inherited from [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)**

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/#property-xmlname)**  |


## Public Functions Documentation

### function Create

```csharp
static SerializableAction Create(
    ElementInfo info,
    SerializableAction action
)
```


### function ActionDelayDecorator

```csharp
ActionDelayDecorator(
    ElementInfo info,
    SerializableAction action
)
```


### function Trigger

```csharp
override void Trigger(
    OS os
)
```


### function GetSaveElement

```csharp
virtual override XElement GetSaveElement()
```


**Reimplements**: [Pathfinder::Action::PathfinderAction::GetSaveElement](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#function-getsaveelement)


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000