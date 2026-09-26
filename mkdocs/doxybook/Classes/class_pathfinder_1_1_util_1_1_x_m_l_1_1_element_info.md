---
title: Pathfinder::Util::XML::ElementInfo

---

# Pathfinder::Util::XML::ElementInfo





## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-elementinfo)**() |
| | **[ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-elementinfo)**(string name, string content =null, Dictionary< string, string > attributes =null, List< [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) > children =null, [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) parent =null) |
| override string | **[ToString](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-tostring)**() |
| bool | **[TryContentAsBoolean](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-trycontentasboolean)**(out bool result) |
| bool | **[TryContentAsInt](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-trycontentasint)**(out int result) |
| bool | **[TryContentAsFloat](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-trycontentasfloat)**(out float result) |
| bool | **[GetContentAsBoolean](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getcontentasboolean)**(bool defaultVal =default) =default |
| int | **[GetContentAsInt](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getcontentasint)**(int defaultVal =default) =default |
| float | **[GetContentAsFloat](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getcontentasfloat)**(float defaultVal =default) =default |
| bool | **[ContentAsBoolean](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-contentasboolean)**() |
| int | **[ContentAsInt](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-contentasint)**() |
| float | **[ContentAsFloat](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-contentasfloat)**() |
| bool | **[TryAttributeAsBoolean](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-tryattributeasboolean)**(string attribName, out bool result) |
| bool | **[TryAttributeAsInt](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-tryattributeasint)**(string attribName, out int result) |
| bool | **[TryAttributeAsFloat](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-tryattributeasfloat)**(string attribName, out float result) |
| bool | **[GetAttributeAsBoolean](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getattributeasboolean)**(string attribName, bool defaultVal =default) =default |
| int | **[GetAttributeAsInt](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getattributeasint)**(string attribName, int defaultVal =default) =default |
| float | **[GetAttributeAsFloat](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getattributeasfloat)**(string attribName, float defaultVal =default) =default |
| bool | **[AttributeAsBoolean](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-attributeasboolean)**(string attribName) |
| int | **[AttributeAsInt](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-attributeasint)**(string attribName) |
| float | **[AttributeAsFloat](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-attributeasfloat)**(string attribName) |
| bool | **[TryAddChild](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-tryaddchild)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| bool | **[TrySetParent](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-trysetparent)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| bool | **[TrySetAttribute](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-trysetattribute)**(string key, string value) |
| bool | **[TryGetAttribute](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-trygetattribute)**(string key, ref string value) |
| [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) | **[AddChild](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-addchild)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) | **[SetParent](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-setparent)**([ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) info) |
| [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) | **[SetAttribute](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-setattribute)**(string key, string value) |
| string | **[GetAttribute](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-getattribute)**(string key, string defaultValue =null) |
| void | **[WriteToXML](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-writetoxml)**(XmlWriter writer) |
| XElement | **[ConvertToXElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-converttoxelement)**() |
| [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) | **[FromText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#function-fromtext)**(string input) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| string | **[Name](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-name)**  |
| string | **[Content](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-content)**  |
| [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) | **[Parent](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-parent)**  |
| Dictionary< string, string > | **[Attributes](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-attributes)**  |
| List< [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) > | **[Children](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-children)**  |
| ulong | **[NodeID](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-nodeid)**  |
| XmlNodeType | **[Type](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-type)**  |
| bool | **[IsText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/#property-istext)**  |

## Public Functions Documentation

### function ElementInfo

```csharp
ElementInfo()
```


### function ElementInfo

```csharp
ElementInfo(
    string name,
    string content =null,
    Dictionary< string, string > attributes =null,
    List< ElementInfo > children =null,
    ElementInfo parent =null
)
```


### function ToString

```csharp
override string ToString()
```


### function TryContentAsBoolean

```csharp
bool TryContentAsBoolean(
    out bool result
)
```


### function TryContentAsInt

```csharp
bool TryContentAsInt(
    out int result
)
```


### function TryContentAsFloat

```csharp
bool TryContentAsFloat(
    out float result
)
```


### function GetContentAsBoolean

```csharp
bool GetContentAsBoolean(
    bool defaultVal =default
) =default
```


### function GetContentAsInt

```csharp
int GetContentAsInt(
    int defaultVal =default
) =default
```


### function GetContentAsFloat

```csharp
float GetContentAsFloat(
    float defaultVal =default
) =default
```


### function ContentAsBoolean

```csharp
bool ContentAsBoolean()
```


### function ContentAsInt

```csharp
int ContentAsInt()
```


### function ContentAsFloat

```csharp
float ContentAsFloat()
```


### function TryAttributeAsBoolean

```csharp
bool TryAttributeAsBoolean(
    string attribName,
    out bool result
)
```


### function TryAttributeAsInt

```csharp
bool TryAttributeAsInt(
    string attribName,
    out int result
)
```


### function TryAttributeAsFloat

```csharp
bool TryAttributeAsFloat(
    string attribName,
    out float result
)
```


### function GetAttributeAsBoolean

```csharp
bool GetAttributeAsBoolean(
    string attribName,
    bool defaultVal =default
) =default
```


### function GetAttributeAsInt

```csharp
int GetAttributeAsInt(
    string attribName,
    int defaultVal =default
) =default
```


### function GetAttributeAsFloat

```csharp
float GetAttributeAsFloat(
    string attribName,
    float defaultVal =default
) =default
```


### function AttributeAsBoolean

```csharp
bool AttributeAsBoolean(
    string attribName
)
```


### function AttributeAsInt

```csharp
int AttributeAsInt(
    string attribName
)
```


### function AttributeAsFloat

```csharp
float AttributeAsFloat(
    string attribName
)
```


### function TryAddChild

```csharp
bool TryAddChild(
    ElementInfo info
)
```


### function TrySetParent

```csharp
bool TrySetParent(
    ElementInfo info
)
```


### function TrySetAttribute

```csharp
bool TrySetAttribute(
    string key,
    string value
)
```


### function TryGetAttribute

```csharp
bool TryGetAttribute(
    string key,
    ref string value
)
```


### function AddChild

```csharp
ElementInfo AddChild(
    ElementInfo info
)
```


### function SetParent

```csharp
ElementInfo SetParent(
    ElementInfo info
)
```


### function SetAttribute

```csharp
ElementInfo SetAttribute(
    string key,
    string value
)
```


### function GetAttribute

```csharp
string GetAttribute(
    string key,
    string defaultValue =null
)
```


### function WriteToXML

```csharp
void WriteToXML(
    XmlWriter writer
)
```


### function ConvertToXElement

```csharp
XElement ConvertToXElement()
```


### function FromText

```csharp
static ElementInfo FromText(
    string input
)
```


## Public Property Documentation

### property Name

```csharp
string Name;
```


### property Content

```csharp
string Content = null;
```


### property Parent

```csharp
ElementInfo Parent;
```


### property Attributes

```csharp
Dictionary< string, string > Attributes = new Dictionary<string, string>();
```


### property Children

```csharp
List< ElementInfo > Children = new List<ElementInfo>();
```


### property NodeID

```csharp
ulong NodeID = freeId++;
```


### property Type

```csharp
XmlNodeType Type;
```


### property IsText

```csharp
bool IsText;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000