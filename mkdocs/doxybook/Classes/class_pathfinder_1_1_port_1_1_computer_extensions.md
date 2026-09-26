---
title: Pathfinder::Port::ComputerExtensions

---

# Pathfinder::Port::ComputerExtensions





## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[AddPort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-addport)**(this Computer comp, string protocol, int portNum, string displayName) |
| void | **[AddPort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-addport)**(this Computer comp, [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) port) |
| void | **[AddPort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-addport)**(this Computer comp, [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record) |
| void | **[AddPort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-addport)**(this Computer comp, [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) port) |
| bool | **[RemovePort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-removeport)**(this Computer comp, string protocol) |
| bool | **[RemovePort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-removeport)**(this Computer comp, [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record) |
| [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) | **[GetPortState](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-getportstate)**(this Computer comp, string protocol) |
| [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) | **[GetPort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-getport)**(this Computer comp, string protocol) |
| List< [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) > | **[GetAllPortStates](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-getallportstates)**(this Computer comp) |
| List< [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) > | **[GetAllPorts](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-getallports)**(this Computer comp) |
| Dictionary< string, [PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/) > | **[GetPortStateDict](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-getportstatedict)**(this Computer comp) |
| Dictionary< string, [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) > | **[GetPortDict](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-getportdict)**(this Computer comp) |
| bool | **[HasInitializedPorts](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-hasinitializedports)**(Computer comp) |
| int | **[CountOpenPorts](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-countopenports)**(this Computer comp) |
| void | **[openPort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-openport)**(this Computer comp, string protocol, string ipFrom) |
| void | **[closePort](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-closeport)**(this Computer comp, string protocol, string ipFrom) |
| bool | **[isPortOpen](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-isportopen)**(this Computer comp, string protocol) |
| void | **[ClearPorts](../Classes/class_pathfinder_1_1_port_1_1_computer_extensions/#function-clearports)**(this Computer comp) |

## Public Functions Documentation

### function AddPort

```csharp
static void AddPort(
    this Computer comp,
    string protocol,
    int portNum,
    string displayName
)
```


### function AddPort

```csharp
static void AddPort(
    this Computer comp,
    PortData port
)
```


### function AddPort

```csharp
static void AddPort(
    this Computer comp,
    PortRecord record
)
```


### function AddPort

```csharp
static void AddPort(
    this Computer comp,
    PortState port
)
```


### function RemovePort

```csharp
static bool RemovePort(
    this Computer comp,
    string protocol
)
```


### function RemovePort

```csharp
static bool RemovePort(
    this Computer comp,
    PortRecord record
)
```


### function GetPortState

```csharp
static PortState GetPortState(
    this Computer comp,
    string protocol
)
```


### function GetPort

```csharp
static PortData GetPort(
    this Computer comp,
    string protocol
)
```


### function GetAllPortStates

```csharp
static List< PortState > GetAllPortStates(
    this Computer comp
)
```


### function GetAllPorts

```csharp
static List< PortData > GetAllPorts(
    this Computer comp
)
```


### function GetPortStateDict

```csharp
static Dictionary< string, PortState > GetPortStateDict(
    this Computer comp
)
```


### function GetPortDict

```csharp
static Dictionary< string, PortData > GetPortDict(
    this Computer comp
)
```


### function HasInitializedPorts

```csharp
static bool HasInitializedPorts(
    Computer comp
)
```


### function CountOpenPorts

```csharp
static int CountOpenPorts(
    this Computer comp
)
```


### function openPort

```csharp
static void openPort(
    this Computer comp,
    string protocol,
    string ipFrom
)
```


### function closePort

```csharp
static void closePort(
    this Computer comp,
    string protocol,
    string ipFrom
)
```


### function isPortOpen

```csharp
static bool isPortOpen(
    this Computer comp,
    string protocol
)
```


### function ClearPorts

```csharp
static void ClearPorts(
    this Computer comp
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000