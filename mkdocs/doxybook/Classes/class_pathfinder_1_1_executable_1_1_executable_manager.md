---
title: Pathfinder::Executable::ExecutableManager

---

# Pathfinder::Executable::ExecutableManager





## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[CustomExeInfo](../Classes/struct_pathfinder_1_1_executable_1_1_executable_manager_1_1_custom_exe_info/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[RegisterExecutable< T >](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-registerexecutable<-t->)**(string xmlName) |
| void | **[RegisterExecutable](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-registerexecutable)**(Type executableType, string xmlName) |
| bool | **[IsXmlId](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-isxmlid)**(string xmlName) |
| bool | **[IsExeData](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-isexedata)**(string exeData) |
| bool | **[IsRegistered< T >](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-isregistered<-t->)**() |
| bool | **[IsRegistered](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-isregistered)**(Type exeType) |
| string | **[GetCustomExeData](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-getcustomexedata)**(string xmlName) |
| void | **[UnregisterExecutable](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-unregisterexecutable)**(string xmlName) |
| void | **[UnregisterExecutable< T >](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-unregisterexecutable<-t->)**() |
| void | **[UnregisterExecutable](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-unregisterexecutable)**(Type exeType) |
| void | **[AddGameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-addgameexecutable)**(this OS os, [GameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/) exe, Rectangle location, string[] args) |
| void | **[AddGameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#function-addgameexecutable)**(this OS os, [GameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/) exe) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| IReadOnlyList< [CustomExeInfo](../Classes/struct_pathfinder_1_1_executable_1_1_executable_manager_1_1_custom_exe_info/) > | **[AllCustomExes](../Classes/class_pathfinder_1_1_executable_1_1_executable_manager/#property-allcustomexes)**  |

## Public Functions Documentation

### function RegisterExecutable< T >

```csharp
static void RegisterExecutable< T >(
    string xmlName
)
```


### function RegisterExecutable

```csharp
static void RegisterExecutable(
    Type executableType,
    string xmlName
)
```


### function IsXmlId

```csharp
static bool IsXmlId(
    string xmlName
)
```


### function IsExeData

```csharp
static bool IsExeData(
    string exeData
)
```


### function IsRegistered< T >

```csharp
static bool IsRegistered< T >()
```


### function IsRegistered

```csharp
static bool IsRegistered(
    Type exeType
)
```


### function GetCustomExeData

```csharp
static string GetCustomExeData(
    string xmlName
)
```


### function UnregisterExecutable

```csharp
static void UnregisterExecutable(
    string xmlName
)
```


### function UnregisterExecutable< T >

```csharp
static void UnregisterExecutable< T >()
```


### function UnregisterExecutable

```csharp
static void UnregisterExecutable(
    Type exeType
)
```


### function AddGameExecutable

```csharp
static void AddGameExecutable(
    this OS os,
    GameExecutable exe,
    Rectangle location,
    string[] args
)
```


### function AddGameExecutable

```csharp
static void AddGameExecutable(
    this OS os,
    GameExecutable exe
)
```


## Public Property Documentation

### property AllCustomExes

```csharp
static IReadOnlyList< CustomExeInfo > AllCustomExes;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000