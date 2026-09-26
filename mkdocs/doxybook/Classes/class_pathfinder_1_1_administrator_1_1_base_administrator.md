---
title: Pathfinder::Administrator::BaseAdministrator

---

# Pathfinder::Administrator::BaseAdministrator





Inherits from Hacknet.Administrator, [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)

Inherited by [ExampleMod2.TestAdministrator](../Classes/class_example_mod2_1_1_test_administrator/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#function-baseadministrator)**(Computer computer, OS opSystem) |
| virtual void | **[LoadFromXml](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| virtual XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#function-getsaveelement)**() |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#property-xmlname)**  |

## Protected Attributes

|                | Name           |
| -------------- | -------------- |
| Computer | **[computer](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#variable-computer)**  |
| OS | **[opSystem](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#variable-opsystem)**  |

## Public Functions Documentation

### function BaseAdministrator

```csharp
BaseAdministrator(
    Computer computer,
    OS opSystem
)
```


### function LoadFromXml

```csharp
virtual void LoadFromXml(
    ElementInfo info
)
```


### function GetSaveElement

```csharp
virtual XElement GetSaveElement()
```


## Public Property Documentation

### property XmlName

```csharp
string XmlName;
```


**Reimplements**: [Pathfinder::Util::IXmlName::XmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/#property-xmlname)


## Protected Attributes Documentation

### variable computer

```csharp
Computer computer;
```


### variable opSystem

```csharp
OS opSystem;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000