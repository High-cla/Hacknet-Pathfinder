---
title: Pathfinder::Daemon::BaseDaemon

---

# Pathfinder::Daemon::BaseDaemon





Inherits from Hacknet.Daemon

Inherited by [ExampleMod2.TestDaemon](../Classes/class_example_mod2_1_1_test_daemon/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[BaseDaemon](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-basedaemon)**(Computer computer, string serviceName, OS opSystem) |
| override string | **[getSaveString](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-getsavestring)**()<br>DO NOT USE! This is a stubbed version of the base game method and is never saved by [Pathfinder](../Namespaces/namespace_pathfinder/).  |
| virtual XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-getsaveelement)**() |
| virtual void | **[LoadFromXml](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| string | **[Identifier](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#property-identifier)**  |

## Public Functions Documentation

### function BaseDaemon

```csharp
BaseDaemon(
    Computer computer,
    string serviceName,
    OS opSystem
)
```


### function getSaveString

```csharp
override string getSaveString()
```

DO NOT USE! This is a stubbed version of the base game method and is never saved by [Pathfinder](../Namespaces/namespace_pathfinder/). 

**Return**: Returns null always

### function GetSaveElement

```csharp
virtual XElement GetSaveElement()
```


### function LoadFromXml

```csharp
virtual void LoadFromXml(
    ElementInfo info
)
```


## Public Property Documentation

### property Identifier

```csharp
string Identifier;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000