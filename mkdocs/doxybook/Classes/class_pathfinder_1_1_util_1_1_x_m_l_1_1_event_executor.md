---
title: Pathfinder::Util::XML::EventExecutor

---

# Pathfinder::Util::XML::EventExecutor





Inherits from [Pathfinder.Util.XML.EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[EventExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-eventexecutor)**() |
| | **[EventExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-eventexecutor)**(string text, bool isPath) |
| | **[EventExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-eventexecutor)**(XmlReader rdr) |
| void | **[SaveState](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-savestate)**() |
| void | **[PopState](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-popstate)**() |
| void | **[RegisterExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-registerexecutor)**(string element, [ReadExecution](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#function-readexecution) executor, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =[ParseOption.None](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enumvalue-none)) |
| void | **[RegisterTempExecutor](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-registertempexecutor)**(string element, [ReadExecution](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#function-readexecution) executor, [ParseOption](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enum-parseoption) options =[ParseOption.None](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/#enumvalue-none)) |

## Protected Functions

|                | Name           |
| -------------- | -------------- |
| virtual override void | **[ReadElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-readelement)**(Dictionary< string, string > attributes) |
| virtual override void | **[ReadEndElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-readendelement)**() |
| virtual override void | **[ReadText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-readtext)**() |
| virtual override void | **[EndRead](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_executor/#function-endread)**() |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Util.XML.EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**

|                | Name           |
| -------------- | -------------- |
| | **[EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-eventreader)**() |
| | **[EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-eventreader)**(string text, bool isPath) |
| | **[EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-eventreader)**(XmlReader rdr) |
| void | **[SetText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-settext)**(string text, bool isPath) |
| void | **[Parse](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-parse)**() |
| bool | **[TryParse](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-tryparse)**(out Exception exception) |

**Protected Functions inherited from [Pathfinder.Util.XML.EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**

|                | Name           |
| -------------- | -------------- |
| virtual bool | **[Read](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-read)**() |
| virtual bool | **[ReadDocument](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readdocument)**() |

**Public Properties inherited from [Pathfinder.Util.XML.EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**

|                | Name           |
| -------------- | -------------- |
| XmlReader | **[Reader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#property-reader)**  |
| string | **[CurrentNamespace](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#property-currentnamespace)**  |

**Public Attributes inherited from [Pathfinder.Util.XML.EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**

|                | Name           |
| -------------- | -------------- |
| List< string > | **[ParentNames](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#variable-parentnames)**  |

**Protected Attributes inherited from [Pathfinder.Util.XML.EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**

|                | Name           |
| -------------- | -------------- |
| string | **[Text](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#variable-text)**  |


## Public Functions Documentation

### function EventExecutor

```csharp
EventExecutor()
```


### function EventExecutor

```csharp
EventExecutor(
    string text,
    bool isPath
)
```


### function EventExecutor

```csharp
EventExecutor(
    XmlReader rdr
)
```


### function SaveState

```csharp
void SaveState()
```


### function PopState

```csharp
void PopState()
```


### function RegisterExecutor

```csharp
void RegisterExecutor(
    string element,
    ReadExecution executor,
    ParseOption options =ParseOption.None
)
```


### function RegisterTempExecutor

```csharp
void RegisterTempExecutor(
    string element,
    ReadExecution executor,
    ParseOption options =ParseOption.None
)
```


## Protected Functions Documentation

### function ReadElement

```csharp
virtual override void ReadElement(
    Dictionary< string, string > attributes
)
```


**Reimplements**: [Pathfinder::Util::XML::EventReader::ReadElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readelement)


### function ReadEndElement

```csharp
virtual override void ReadEndElement()
```


**Reimplements**: [Pathfinder::Util::XML::EventReader::ReadEndElement](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readendelement)


### function ReadText

```csharp
virtual override void ReadText()
```


**Reimplements**: [Pathfinder::Util::XML::EventReader::ReadText](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-readtext)


### function EndRead

```csharp
virtual override void EndRead()
```


**Reimplements**: [Pathfinder::Util::XML::EventReader::EndRead](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/#function-endread)


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000