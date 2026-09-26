---
title: Pathfinder::Port::PortRecord

---

# Pathfinder::Port::PortRecord





Inherits from IEquatable< PortRecord >

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-portrecord)**(string protocol, string defDisplayName, int defPortNumber) |
| [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) | **[CreateState](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-createstate)**(Computer computer, string displayName =null, int portNumber =-1, bool cracked =false) |
| [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) | **[CreateState](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-createstate)**(Computer computer, bool cracked) |
| bool | **[Equals](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-equals)**([PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) other) |
| override bool | **[Equals](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-equals)**(object obj) |
| override int | **[GetHashCode](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-gethashcode)**() |
| bool | **[operator==](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-operator==)**([PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) first, [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) second) |
| bool | **[operator!=](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-operator!=)**([PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) first, [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) second) |
| static | **[operator PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-operator-portrecord)**([PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) data) |
| static | **[operator PortData](../Classes/class_pathfinder_1_1_port_1_1_port_record/#function-operator-portdata)**([PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| string | **[Protocol](../Classes/class_pathfinder_1_1_port_1_1_port_record/#property-protocol)**  |
| int | **[OriginalPortNumber](../Classes/class_pathfinder_1_1_port_1_1_port_record/#property-originalportnumber)**  |
| string | **[DefaultDisplayName](../Classes/class_pathfinder_1_1_port_1_1_port_record/#property-defaultdisplayname)**  |
| int | **[DefaultPortNumber](../Classes/class_pathfinder_1_1_port_1_1_port_record/#property-defaultportnumber)**  |

## Public Functions Documentation

### function PortRecord

```csharp
PortRecord(
    string protocol,
    string defDisplayName,
    int defPortNumber
)
```


### function CreateState

```csharp
PortState CreateState(
    Computer computer,
    string displayName =null,
    int portNumber =-1,
    bool cracked =false
)
```


### function CreateState

```csharp
PortState CreateState(
    Computer computer,
    bool cracked
)
```


### function Equals

```csharp
bool Equals(
    PortRecord other
)
```


### function Equals

```csharp
override bool Equals(
    object obj
)
```


### function GetHashCode

```csharp
override int GetHashCode()
```


### function operator==

```csharp
static bool operator==(
    PortRecord first,
    PortRecord second
)
```


### function operator!=

```csharp
static bool operator!=(
    PortRecord first,
    PortRecord second
)
```


### function operator PortRecord

```csharp
static explicit static operator PortRecord(
    PortData data
)
```


### function operator PortData

```csharp
static explicit static operator PortData(
    PortRecord record
)
```


## Public Property Documentation

### property Protocol

```csharp
string Protocol;
```


### property OriginalPortNumber

```csharp
int OriginalPortNumber;
```


### property DefaultDisplayName

```csharp
string DefaultDisplayName;
```


### property DefaultPortNumber

```csharp
int DefaultPortNumber;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000