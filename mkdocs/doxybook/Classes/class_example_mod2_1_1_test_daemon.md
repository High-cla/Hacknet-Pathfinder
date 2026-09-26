---
title: ExampleMod2::TestDaemon

---

# ExampleMod2::TestDaemon





Inherits from [Pathfinder.Daemon.BaseDaemon](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/), Hacknet.Daemon

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[TestDaemon](../Classes/class_example_mod2_1_1_test_daemon/#function-testdaemon)**(Computer computer, string serviceName, OS opSystem) |
| override void | **[draw](../Classes/class_example_mod2_1_1_test_daemon/#function-draw)**(Rectangle bounds, SpriteBatch sb) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| override string | **[Identifier](../Classes/class_example_mod2_1_1_test_daemon/#property-identifier)**  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| string | **[DisplayString](../Classes/class_example_mod2_1_1_test_daemon/#variable-displaystring)**  |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Daemon.BaseDaemon](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/)**

|                | Name           |
| -------------- | -------------- |
| | **[BaseDaemon](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-basedaemon)**(Computer computer, string serviceName, OS opSystem) |
| override string | **[getSaveString](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-getsavestring)**()<br>DO NOT USE! This is a stubbed version of the base game method and is never saved by [Pathfinder](../Namespaces/namespace_pathfinder/).  |
| virtual XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-getsaveelement)**() |
| virtual void | **[LoadFromXml](../Classes/class_pathfinder_1_1_daemon_1_1_base_daemon/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |


## Public Functions Documentation

### function TestDaemon

```csharp
TestDaemon(
    Computer computer,
    string serviceName,
    OS opSystem
)
```


### function draw

```csharp
override void draw(
    Rectangle bounds,
    SpriteBatch sb
)
```


## Public Property Documentation

### property Identifier

```csharp
override string Identifier;
```


## Public Attributes Documentation

### variable DisplayString

```csharp
string DisplayString;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000