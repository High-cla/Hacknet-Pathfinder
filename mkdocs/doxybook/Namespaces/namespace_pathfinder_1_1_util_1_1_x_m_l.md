---
title: Pathfinder::Util::XML

---

# Pathfinder::Util::XML



## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::XML::ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/)**  |
| class | **[Pathfinder::Util::XML::ElementInfoDictionaryExtensions](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info_dictionary_extensions/)**  |
| class | **[Pathfinder::Util::XML::ElementInfoListExtensions](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info_list_extensions/)**  |
| class | **[Pathfinder::Util::XML::ElementInfoStringExtensions](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info_string_extensions/)**  |
| class | **[Pathfinder::Util::XML::EventExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/)**  |
| class | **[Pathfinder::Util::XML::EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**  |
| class | **[Pathfinder::Util::XML::ListExtensions](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_list_extensions/)**  |

## Types

|                | Name           |
| -------------- | -------------- |
| enum class| **[ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption)** { None = 0, ParseInterior = 0b1, FireOnEnd = 0b10, DontAllowOthers = 0b100} |

## Functions

|                | Name           |
| -------------- | -------------- |
| delegate void | **[ReadExecution](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#function-readexecution)**([EventExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/) exec, [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

## Types Documentation

### enum ParseOption

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| None | 0|   |
| ParseInterior | 0b1|   |
| FireOnEnd | 0b10|   |
| DontAllowOthers | 0b100|   |





## Functions Documentation

### function ReadExecution

```csharp
delegate void ReadExecution(
    EventExecutor exec,
    ElementInfo info
)
```






-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000