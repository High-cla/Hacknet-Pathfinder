---
title: ExampleMod2::TestGoal

---

# ExampleMod2::TestGoal





Inherits from [Pathfinder.Mission.PathfinderGoal](../Classes/class_pathfinder_1_1_mission_1_1_pathfinder_goal/), MisisonGoal

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual override void | **[LoadFromXML](../Classes/class_example_mod2_1_1_test_goal/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| override bool | **[isComplete](../Classes/class_example_mod2_1_1_test_goal/#function-iscomplete)**(List< string > additionalDetails =null) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| string | **[NodeID](../Classes/class_example_mod2_1_1_test_goal/#variable-nodeid)**  |
| string | **[OriginalIP](../Classes/class_example_mod2_1_1_test_goal/#variable-originalip)**  |

## Public Functions Documentation

### function LoadFromXML

```csharp
virtual override void LoadFromXML(
    ElementInfo info
)
```


**Reimplements**: [Pathfinder::Mission::PathfinderGoal::LoadFromXML](../Classes/class_pathfinder_1_1_mission_1_1_pathfinder_goal/#function-loadfromxml)


### function isComplete

```csharp
override bool isComplete(
    List< string > additionalDetails =null
)
```


## Public Attributes Documentation

### variable NodeID

```csharp
string NodeID;
```


### variable OriginalIP

```csharp
string OriginalIP;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000