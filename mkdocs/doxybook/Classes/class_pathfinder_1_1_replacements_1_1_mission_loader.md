---
title: Pathfinder::Replacements::MissionLoader

---

# Pathfinder::Replacements::MissionLoader





## Public Classes

|                | Name           |
| -------------- | -------------- |
| class | **[MissionExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_mission_loader_1_1_mission_executor/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[RegisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_mission_loader/#function-registerexecutor<-t->)**(string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[RegisterExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_mission_loader/#function-registerexecutor)**(Type executorType, string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[UnregisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_mission_loader/#function-unregisterexecutor<-t->)**() |
| ActiveMission | **[LoadContentMission](../Classes/class_pathfinder_1_1_replacements_1_1_mission_loader/#function-loadcontentmission)**(string filename) |
| MisisonGoal | **[LoadGoal](../Classes/class_pathfinder_1_1_replacements_1_1_mission_loader/#function-loadgoal)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

## Public Functions Documentation

### function RegisterExecutor< T >

```csharp
static void RegisterExecutor< T >(
    string element,
    ParseOption options =ParseOption.None
)
```


### function RegisterExecutor

```csharp
static void RegisterExecutor(
    Type executorType,
    string element,
    ParseOption options =ParseOption.None
)
```


### function UnregisterExecutor< T >

```csharp
static void UnregisterExecutor< T >()
```


### function LoadContentMission

```csharp
static ActiveMission LoadContentMission(
    string filename
)
```


### function LoadGoal

```csharp
static MisisonGoal LoadGoal(
    ElementInfo info
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000