---
title: Pathfinder::Action::DelayablePathfinderAction

---

# Pathfinder::Action::DelayablePathfinderAction





Inherits from [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/), SerializableAction, [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)

Inherited by [ExampleMod2.TestAction](../Classes/class_example_mod2_1_1_test_action/), [Pathfinder.Action.ActionDelayDecorator](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| override void | **[Trigger](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#function-trigger)**(object os_obj) |
| void | **[Trigger](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#function-trigger)**(OS os) |
| virtual override void | **[LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| string | **[DelayHost](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#variable-delayhost)**  |
| string | **[Delay](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#variable-delay)**  |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| virtual XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#function-getsaveelement)**() |

**Public Properties inherited from [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#property-xmlname)**  |

**Public Properties inherited from [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)**

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/#property-xmlname)**  |


## Public Functions Documentation

### function Trigger

```csharp
override void Trigger(
    object os_obj
)
```


### function Trigger

```csharp
void Trigger(
    OS os
)
```


### function LoadFromXml

```csharp
virtual override void LoadFromXml(
    ElementInfo info
)
```


**Reimplements**: [Pathfinder::Action::PathfinderAction::LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#function-loadfromxml)


**Reimplemented by**: [ExampleMod2::TestAction::LoadFromXml](../Classes/class_example_mod2_1_1_test_action/#function-loadfromxml)


## Public Attributes Documentation

### variable DelayHost

```csharp
string DelayHost;
```


### variable Delay

```csharp
string Delay;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000