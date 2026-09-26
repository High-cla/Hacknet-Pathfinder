---
title: Pathfinder::Port::PortManager

---

# Pathfinder::Port::PortManager





## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[RegisterPort](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-registerport)**(string protocol, string displayName, int defaultPort =-1) |
| void | **[RegisterPort](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-registerport)**([PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) info) |
| void | **[RegisterPort](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-registerport)**([PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record) |
| void | **[UnregisterPort](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-unregisterport)**(string protocol, Assembly pluginAsm =null) |
| bool | **[IsPortRecordRegistered](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-isportrecordregistered)**([PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) record) |
| bool | **[IsPortRegistered](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-isportregistered)**(string protocol) |
| [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) | **[GetPortRecordFromProtocol](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-getportrecordfromprotocol)**(string proto) |
| [PortRecord](../Classes/class_pathfinder_1_1_port_1_1_port_record/) | **[GetPortRecordFromNumber](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-getportrecordfromnumber)**(int num) |
| [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) | **[GetPortDataFromProtocol](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-getportdatafromprotocol)**(string proto) |
| [PortData](../Classes/class_pathfinder_1_1_port_1_1_port_data/) | **[GetPortDataFromNumber](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-getportdatafromnumber)**(int num) |
| void | **[LoadPortsFromChildren](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-loadportsfromchildren)**(Computer comp, IEnumerable< [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) > children, bool clearAll) |
| void | **[LoadPortsFromString](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-loadportsfromstring)**(Computer comp, string portString, bool clearExisting) |
| void | **[LoadPortsFromStringVanilla](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-loadportsfromstringvanilla)**(Computer comp, string portsList) |
| void | **[LoadPortRemapsFromStringVanilla](../Classes/class_pathfinder_1_1_port_1_1_port_manager/#function-loadportremapsfromstringvanilla)**(Computer comp, string remap) |

## Public Functions Documentation

### function RegisterPort

```csharp
static void RegisterPort(
    string protocol,
    string displayName,
    int defaultPort =-1
)
```


### function RegisterPort

```csharp
static void RegisterPort(
    PortData info
)
```


### function RegisterPort

```csharp
static void RegisterPort(
    PortRecord record
)
```


### function UnregisterPort

```csharp
static void UnregisterPort(
    string protocol,
    Assembly pluginAsm =null
)
```


### function IsPortRecordRegistered

```csharp
static bool IsPortRecordRegistered(
    PortRecord record
)
```


### function IsPortRegistered

```csharp
static bool IsPortRegistered(
    string protocol
)
```


### function GetPortRecordFromProtocol

```csharp
static PortRecord GetPortRecordFromProtocol(
    string proto
)
```


### function GetPortRecordFromNumber

```csharp
static PortRecord GetPortRecordFromNumber(
    int num
)
```


### function GetPortDataFromProtocol

```csharp
static PortData GetPortDataFromProtocol(
    string proto
)
```


### function GetPortDataFromNumber

```csharp
static PortData GetPortDataFromNumber(
    int num
)
```


### function LoadPortsFromChildren

```csharp
static void LoadPortsFromChildren(
    Computer comp,
    IEnumerable< ElementInfo > children,
    bool clearAll
)
```


### function LoadPortsFromString

```csharp
static void LoadPortsFromString(
    Computer comp,
    string portString,
    bool clearExisting
)
```


### function LoadPortsFromStringVanilla

```csharp
static void LoadPortsFromStringVanilla(
    Computer comp,
    string portsList
)
```


### function LoadPortRemapsFromStringVanilla

```csharp
static void LoadPortRemapsFromStringVanilla(
    Computer comp,
    string remap
)
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000