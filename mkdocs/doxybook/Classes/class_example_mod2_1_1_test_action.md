---
title: ExampleMod2::TestAction

---

# ExampleMod2::TestAction





Inherits from [Pathfinder.Action.DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/), [Pathfinder.Action.PathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_pathfinder_action/), SerializableAction, [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| override void | **[Trigger](../Classes/class_example_mod2_1_1_test_action/#function-trigger)**(OS os) |
| virtual override void | **[LoadFromXml](../Classes/class_example_mod2_1_1_test_action/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| string | **[Min](../Classes/class_example_mod2_1_1_test_action/#variable-min)**  |
| string | **[Max](../Classes/class_example_mod2_1_1_test_action/#variable-max)**  |
| string | **[stringToWrite](../Classes/class_example_mod2_1_1_test_action/#variable-stringtowrite)**  |

## Additional inherited members

**Public Attributes inherited from [Pathfinder.Action.DelayablePathfinderAction](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/)**

|                | Name           |
| -------------- | -------------- |
| string | **[DelayHost](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#variable-delayhost)**  |
| string | **[Delay](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#variable-delay)**  |

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
    OS os
)
```


### function LoadFromXml

```csharp
virtual override void LoadFromXml(
    ElementInfo info
)
```


**Reimplements**: [Pathfinder::Action::DelayablePathfinderAction::LoadFromXml](../Classes/class_pathfinder_1_1_action_1_1_delayable_pathfinder_action/#function-loadfromxml)


## Public Attributes Documentation

### variable Min

```csharp
string Min;
```


### variable Max

```csharp
string Max;
```


### variable stringToWrite

```csharp
string stringToWrite;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000