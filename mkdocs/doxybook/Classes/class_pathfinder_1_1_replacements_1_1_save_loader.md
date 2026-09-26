---
title: Pathfinder::Replacements::SaveLoader

---

# Pathfinder::Replacements::SaveLoader





## Public Classes

|                | Name           |
| -------------- | -------------- |
| class | **[SaveExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader_1_1_save_executor/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[RegisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader/#function-registerexecutor<-t->)**(string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[RegisterExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader/#function-registerexecutor)**(Type executorType, string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[UnregisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader/#function-unregisterexecutor<-t->)**() |
| Computer | **[LoadComputer](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader/#function-loadcomputer)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info, OS os) |
| Folder | **[LoadFolder](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader/#function-loadfolder)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| ActiveMission | **[LoadMission](../Classes/class_pathfinder_1_1_replacements_1_1_save_loader/#function-loadmission)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) root) |

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


### function LoadComputer

```csharp
static Computer LoadComputer(
    ElementInfo info,
    OS os
)
```


### function LoadFolder

```csharp
static Folder LoadFolder(
    ElementInfo info
)
```


### function LoadMission

```csharp
static ActiveMission LoadMission(
    ElementInfo root
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000