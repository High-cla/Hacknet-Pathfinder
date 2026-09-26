---
title: Pathfinder::Event::Gameplay::ExecutableListEvent

---

# Pathfinder::Event::Gameplay::ExecutableListEvent





Inherits from [Pathfinder.Event.PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[ExecutableListEvent](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_list_event/#function-executablelistevent)**([OS](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_list_event/#property-os) os, Dictionary< FileEntry, bool > binExes) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| OS | **[OS](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_list_event/#property-os)**  |
| List< string > | **[EmbeddedExes](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_list_event/#property-embeddedexes)**  |
| Dictionary< FileEntry, bool > | **[BinExes](../Classes/class_pathfinder_1_1_event_1_1_gameplay_1_1_executable_list_event/#property-binexes)**  |

## Additional inherited members

**Public Properties inherited from [Pathfinder.Event.PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)**

|                | Name           |
| -------------- | -------------- |
| bool | **[Cancelled](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/#property-cancelled)**  |
| bool | **[Thrown](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/#property-thrown)**  |


## Public Functions Documentation

### function ExecutableListEvent

```csharp
ExecutableListEvent(
    OS os,
    Dictionary< FileEntry, bool > binExes
)
```


## Public Property Documentation

### property OS

```csharp
OS OS;
```


### property EmbeddedExes

```csharp
List< string > EmbeddedExes = new List<string>
    {
        "PortHack", "ForkBomb", "Shell", "Tutorial"
    };
```


### property BinExes

```csharp
Dictionary< FileEntry, bool > BinExes;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000