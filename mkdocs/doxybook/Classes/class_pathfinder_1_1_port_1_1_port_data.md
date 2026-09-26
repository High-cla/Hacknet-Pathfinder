---
title: Pathfinder::Port::PortData

---

# Pathfinder::Port::PortData





Inherits from IEquatable< PortData >

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-portdata)**(string proto, int portNum, string displayName) |
| [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) | **[Clone](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-clone)**() |
| bool | **[Equals](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-equals)**([PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) other) |
| override bool | **[Equals](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-equals)**(object obj) |
| override int | **[GetHashCode](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-gethashcode)**() |
| bool | **[operator==](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-operator==)**([PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) first, [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) second) |
| bool | **[operator!=](../Classes/class_pathfinder_1_1_port_1_1_port_data/#function-operator!=)**([PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) first, [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) second) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| string | **[Protocol](../Classes/class_pathfinder_1_1_port_1_1_port_data/#property-protocol)**  |
| string | **[DisplayName](../Classes/class_pathfinder_1_1_port_1_1_port_data/#property-displayname)**  |
| int | **[Port](../Classes/class_pathfinder_1_1_port_1_1_port_data/#property-port)**  |
| int | **[OriginalPort](../Classes/class_pathfinder_1_1_port_1_1_port_data/#property-originalport)**  |
| bool | **[Cracked](../Classes/class_pathfinder_1_1_port_1_1_port_data/#property-cracked)**  |

## Public Functions Documentation

### function PortData

```csharp
PortData(
    string proto,
    int portNum,
    string displayName
)
```


### function Clone

```csharp
PortData Clone()
```


### function Equals

```csharp
bool Equals(
    PortData other
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
    PortData first,
    PortData second
)
```


### function operator!=

```csharp
static bool operator!=(
    PortData first,
    PortData second
)
```


## Public Property Documentation

### property Protocol

```csharp
string Protocol;
```


### property DisplayName

```csharp
string DisplayName;
```


### property Port

```csharp
int Port;
```


### property OriginalPort

```csharp
int OriginalPort;
```


### property Cracked

```csharp
bool Cracked = false;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000