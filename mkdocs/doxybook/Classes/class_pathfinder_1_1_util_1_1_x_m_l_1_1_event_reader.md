---
title: Pathfinder::Util::XML::EventReader

---

# Pathfinder::Util::XML::EventReader





Inherited by [Pathfinder.Util.XML.EventExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-eventreader)**() |
| | **[EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-eventreader)**(string text, bool isPath) |
| | **[EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-eventreader)**(XmlReader rdr) |
| void | **[SetText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-settext)**(string text, bool isPath) |
| void | **[Parse](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-parse)**() |
| bool | **[TryParse](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-tryparse)**(out Exception exception) |

## Protected Functions

|                | Name           |
| -------------- | -------------- |
| virtual bool | **[Read](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-read)**() |
| virtual bool | **[ReadDocument](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readdocument)**() |
| virtual void | **[ReadElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readelement)**(Dictionary< string, string > attributes) |
| virtual void | **[ReadEndElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readendelement)**() |
| virtual void | **[ReadText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readtext)**() |
| virtual void | **[EndRead](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-endread)**() |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| XmlReader | **[Reader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#property-reader)**  |
| string | **[CurrentNamespace](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#property-currentnamespace)**  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| List< string > | **[ParentNames](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#variable-parentnames)**  |

## Protected Attributes

|                | Name           |
| -------------- | -------------- |
| string | **[Text](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#variable-text)**  |

## Public Functions Documentation

### function EventReader

```csharp
EventReader()
```


### function EventReader

```csharp
EventReader(
    string text,
    bool isPath
)
```


### function EventReader

```csharp
EventReader(
    XmlReader rdr
)
```


### function SetText

```csharp
void SetText(
    string text,
    bool isPath
)
```


### function Parse

```csharp
void Parse()
```


### function TryParse

```csharp
bool TryParse(
    out Exception exception
)
```


## Protected Functions Documentation

### function Read

```csharp
virtual bool Read()
```


### function ReadDocument

```csharp
virtual bool ReadDocument()
```


### function ReadElement

```csharp
virtual void ReadElement(
    Dictionary< string, string > attributes
)
```


**Reimplemented by**: [Pathfinder::Util::XML::EventExecutor::ReadElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-readelement)


### function ReadEndElement

```csharp
virtual void ReadEndElement()
```


**Reimplemented by**: [Pathfinder::Util::XML::EventExecutor::ReadEndElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-readendelement)


### function ReadText

```csharp
virtual void ReadText()
```


**Reimplemented by**: [Pathfinder::Util::XML::EventExecutor::ReadText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-readtext)


### function EndRead

```csharp
virtual void EndRead()
```


**Reimplemented by**: [Pathfinder::Util::XML::EventExecutor::EndRead](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-endread)


## Public Property Documentation

### property Reader

```csharp
XmlReader Reader;
```


### property CurrentNamespace

```csharp
string CurrentNamespace;
```


## Public Attributes Documentation

### variable ParentNames

```csharp
List< string > ParentNames = new List<string>();
```


## Protected Attributes Documentation

### variable Text

```csharp
string Text;
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000