---
title: Pathfinder::Action::PathfinderAction

---

# Pathfinder::Action::PathfinderAction





Inherits from SerializableAction, [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)

Inherited by [Pathfinder.Action.DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#function-getsaveelement)**() |
| virtual void | **[LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/#property-xmlname)**  |

## Public Functions Documentation

### function GetSaveElement

```csharp
virtual XElement GetSaveElement()
```


**Reimplemented by**: [Pathfinder::Action::ActionDelayDecorator::GetSaveElement](../Classes/class_pathfinder_1_1_action_1_1_action_delay_decorator/#function-getsaveelement)


### function LoadFromXml

```csharp
virtual void LoadFromXml(
    ElementInfo info
)
```


**Reimplemented by**: [ExampleMod2::TestAction::LoadFromXml](../Classes/class_example_mod2_1_1_test_action/#function-loadfromxml), [Pathfinder::Action::DelayablePathfinderAction::LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#function-loadfromxml)


## Public Property Documentation

### property XmlName

```csharp
string XmlName;
```


**Reimplements**: [Pathfinder::Util::IXmlName::XmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/#property-xmlname)


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000