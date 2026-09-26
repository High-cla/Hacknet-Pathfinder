---
title: Pathfinder::Replacements::ExtensionInfoLoader

---

# Pathfinder::Replacements::ExtensionInfoLoader





## Public Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ExtensionInfoExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_extension_info_loader_1_1_extension_info_executor/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[AddLanguage](../Classes/class_pathfinder_1_1_replacements_1_1_extension_info_loader/#function-addlanguage)**(string language) |
| void | **[RegisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_extension_info_loader/#function-registerexecutor<-t->)**(string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[RegisterExecutor](../Classes/class_pathfinder_1_1_replacements_1_1_extension_info_loader/#function-registerexecutor)**(Type executorType, string element, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =ParseOption.None) |
| void | **[UnregisterExecutor< T >](../Classes/class_pathfinder_1_1_replacements_1_1_extension_info_loader/#function-unregisterexecutor<-t->)**() |
| ExtensionInfo | **[LoadExtensionInfo](../Classes/class_pathfinder_1_1_replacements_1_1_extension_info_loader/#function-loadextensioninfo)**(string folderpath) |

## Public Functions Documentation

### function AddLanguage

```csharp
static void AddLanguage(
    string language
)
```


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


### function LoadExtensionInfo

```csharp
static ExtensionInfo LoadExtensionInfo(
    string folderpath
)
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000