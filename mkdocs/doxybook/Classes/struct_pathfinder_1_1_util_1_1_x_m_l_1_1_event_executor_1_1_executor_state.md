---
title: Pathfinder::Util::XML::EventExecutor::ExecutorState

---

# Pathfinder::Util::XML::EventExecutor::ExecutorState





## Public Attributes

|                | Name           |
| -------------- | -------------- |
| XmlReader | **[Reader](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-reader)**  |
| string | **[Text](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-text)**  |
| Dictionary< string, List< ExecutorHolder > > | **[Temps](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-temps)**  |
| Dictionary< string, List< ExecutorHolder > > | **[AllExecs](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-allexecs)**  |
| List< [ReadExecution](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#function-readexecution) > | **[CurrentExecs](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-currentexecs)**  |
| Stack< [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) > | **[ElementStack](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-elementstack)**  |
| List< string > | **[ParentNames](../Classes/struct_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor_1_1_executor_state/#variable-parentnames)**  |

## Public Attributes Documentation

### variable Reader

```csharp
XmlReader Reader;
```


### variable Text

```csharp
string Text;
```


### variable Temps

```csharp
Dictionary< string, List< ExecutorHolder > > Temps;
```


### variable AllExecs

```csharp
Dictionary< string, List< ExecutorHolder > > AllExecs;
```


### variable CurrentExecs

```csharp
List< ReadExecution > CurrentExecs;
```


### variable ElementStack

```csharp
Stack< ElementInfo > ElementStack;
```


### variable ParentNames

```csharp
List< string > ParentNames;
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000