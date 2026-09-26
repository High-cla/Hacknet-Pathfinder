---
title: Pathfinder::Port::PortState

---

# Pathfinder::Port::PortState





## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[SetCracked](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-setcracked)**(bool cracked, string ipFrom) |
| | **[PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-portstate)**([Computer](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-computer) comp, [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record, bool cracked) |
| | **[PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-portstate)**([Computer](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-computer) comp, [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record, string displayName =null, int portNumber =-1, bool cracked =false) |
| | **[PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-portstate)**([Computer](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-computer) comp, string protocol, bool cracked) |
| | **[PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-portstate)**([Computer](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-computer) comp, string protocol, string displayName =null, int portNumber =-1, bool cracked =false) |
| [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) | **[Clone](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-clone)**([Computer](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-computer) comp =null) |
| bool | **[Remove](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-remove)**() |
| static | **[operator PortData](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-operator-portdata)**([PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) state) |
| static | **[operator PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/#function-operator-portstate)**([PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) data) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| Computer | **[Computer](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-computer)**  |
| [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) | **[Record](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-record)**  |
| string | **[DisplayName](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-displayname)**  |
| int | **[PortNumber](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-portnumber)**  |
| bool | **[Cracked](../Classes/class_pathfinder_1_1_port_1_1_port_state/#property-cracked)**  |

## Public Functions Documentation

### function SetCracked

```csharp
void SetCracked(
    bool cracked,
    string ipFrom
)
```


### function PortState

```csharp
PortState(
    Computer comp,
    PortRecord record,
    bool cracked
)
```


### function PortState

```csharp
PortState(
    Computer comp,
    PortRecord record,
    string displayName =null,
    int portNumber =-1,
    bool cracked =false
)
```


### function PortState

```csharp
PortState(
    Computer comp,
    string protocol,
    bool cracked
)
```


### function PortState

```csharp
PortState(
    Computer comp,
    string protocol,
    string displayName =null,
    int portNumber =-1,
    bool cracked =false
)
```


### function Clone

```csharp
PortState Clone(
    Computer comp =null
)
```


### function Remove

```csharp
bool Remove()
```


### function operator PortData

```csharp
static explicit static operator PortData(
    PortState state
)
```


### function operator PortState

```csharp
static explicit static operator PortState(
    PortData data
)
```


## Public Property Documentation

### property Computer

```csharp
Computer Computer;
```


### property Record

```csharp
PortRecord Record;
```


### property DisplayName

```csharp
string DisplayName;
```


### property PortNumber

```csharp
int PortNumber;
```


### property Cracked

```csharp
bool Cracked;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000