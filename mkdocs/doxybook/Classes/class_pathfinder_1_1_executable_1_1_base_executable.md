---
title: Pathfinder::Executable::BaseExecutable

---

# Pathfinder::Executable::BaseExecutable





Inherits from ExeModule

Inherited by [ExampleMod2.TestExe](../Classes/class_example_mod2_1_1_test_exe/), [Pathfinder.Executable.GameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| virtual string | **[GetIdentifier](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/#function-getidentifier)**() |
| | **[BaseExecutable](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/#function-baseexecutable)**(Rectangle location, OS operatingSystem, string[] args) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| string[] | **[Args](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/#variable-args)**  |

## Public Functions Documentation

### function GetIdentifier

```csharp
virtual string GetIdentifier()
```


**Reimplemented by**: [Pathfinder::Executable::GameExecutable::GetIdentifier](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-getidentifier)


### function BaseExecutable

```csharp
BaseExecutable(
    Rectangle location,
    OS operatingSystem,
    string[] args
)
```


## Public Attributes Documentation

### variable Args

```csharp
string[] Args;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000