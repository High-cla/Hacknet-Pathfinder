---
title: Pathfinder::Replacements::ContentLoader

---

# Pathfinder::Replacements::ContentLoader





## Public Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ComputerExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_content_loader_1_1_computer_executor/)**  |
| class | **[ComputerHolder](../Classes/class_pathfinder_1_1_replacements_1_1_content_loader_1_1_computer_holder/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[RegisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_content_loader/#function-registerexecutor<-t->)**(string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[RegisterExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_content_loader/#function-registerexecutor)**(Type executorType, string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[UnregisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_content_loader/#function-unregisterexecutor<-t->)**() |
| Computer | **[LoadComputer](../Classes/class_pathfinder_1_1_replacements_1_1_content_loader/#function-loadcomputer)**(string filename, bool preventAddingToNetmap =false, bool preventInitDaemons =false) |

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
    string filename,
    bool preventAddingToNetmap =false,
    bool preventInitDaemons =false
)
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000