---
title: ExampleMod2::TestAdministrator

---

# ExampleMod2::TestAdministrator





Inherits from [Pathfinder.Administrator.BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/), Hacknet.Administrator, [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[TestAdministrator](../Classes/class_example_mod2_1_1_test_administrator/#function-testadministrator)**(Computer computer, OS opSystem) |
| override void | **[disconnectionDetected](../Classes/class_example_mod2_1_1_test_administrator/#function-disconnectiondetected)**(Computer c, OS os) |
| override void | **[traceEjectionDetected](../Classes/class_example_mod2_1_1_test_administrator/#function-traceejectiondetected)**(Computer c, OS os) |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Administrator.BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/)**

|                | Name           |
| -------------- | -------------- |
| | **[BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#function-baseadministrator)**(Computer computer, OS opSystem) |
| virtual void | **[LoadFromXml](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#function-loadfromxml)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| virtual XElement | **[GetSaveElement](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#function-getsaveelement)**() |

**Public Properties inherited from [Pathfinder.Administrator.BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/)**

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#property-xmlname)**  |

**Protected Attributes inherited from [Pathfinder.Administrator.BaseAdministrator](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/)**

|                | Name           |
| -------------- | -------------- |
| Computer | **[computer](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#variable-computer)**  |
| OS | **[opSystem](../Classes/class_pathfinder_1_1_administrator_1_1_base_administrator/#variable-opsystem)**  |

**Public Properties inherited from [Pathfinder.Util.IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)**

|                | Name           |
| -------------- | -------------- |
| string | **[XmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/#property-xmlname)**  |


## Public Functions Documentation

### function TestAdministrator

```csharp
TestAdministrator(
    Computer computer,
    OS opSystem
)
```


### function disconnectionDetected

```csharp
override void disconnectionDetected(
    Computer c,
    OS os
)
```


### function traceEjectionDetected

```csharp
override void traceEjectionDetected(
    Computer c,
    OS os
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000