---
title: Pathfinder::Event::Gameplay::ExecutableExecuteEvent

---

# Pathfinder::Event::Gameplay::ExecutableExecuteEvent





Inherits from [Pathfinder.Event.PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[ExecutableExecuteEvent](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#function-executableexecuteevent)**([Computer](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-computer) com, [OS](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-os) os, Folder fol, int finde, FileEntry file, string[] args) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| Computer | **[Computer](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-computer)**  |
| OS | **[OS](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-os)**  |
| string | **[ExecutableName](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-executablename)**  |
| string | **[ExecutableData](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-executabledata)**  |
| List< string > | **[Arguments](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-arguments)**  |
| Folder | **[ExeFolder](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-exefolder)**  |
| int | **[FileIndex](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-fileindex)**  |
| FileEntry | **[ExeFile](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-exefile)**  |
| [ExecutionResult](../Namespaces/namespace_pathfinder_1_1_event_1_1_gameplay/#enum-executionresult) | **[Result](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-result)**  |
| string | **[this[int index]](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_execute_event/#property-this[int-index])**  |

## Additional inherited members

**Public Properties inherited from [Pathfinder.Event.PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)**

|                | Name           |
| -------------- | -------------- |
| bool | **[Cancelled](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/#property-cancelled)**  |
| bool | **[Thrown](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/#property-thrown)**  |


## Public Functions Documentation

### function ExecutableExecuteEvent

```csharp
ExecutableExecuteEvent(
    Computer com,
    OS os,
    Folder fol,
    int finde,
    FileEntry file,
    string[] args
)
```


## Public Property Documentation

### property Computer

```csharp
Computer Computer;
```


### property OS

```csharp
OS OS;
```


### property ExecutableName

```csharp
string ExecutableName;
```


### property ExecutableData

```csharp
string ExecutableData;
```


### property Arguments

```csharp
List< string > Arguments;
```


### property ExeFolder

```csharp
Folder ExeFolder;
```


### property FileIndex

```csharp
int FileIndex;
```


### property ExeFile

```csharp
FileEntry ExeFile;
```


### property Result

```csharp
ExecutionResult Result;
```


### property this[int index]

```csharp
string this[int index];
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000