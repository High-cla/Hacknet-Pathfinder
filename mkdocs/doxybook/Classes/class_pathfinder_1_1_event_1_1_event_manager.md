---
title: Pathfinder::Event::EventManager
summary: Manager for PathfinderEvent handlers. 

---

# Pathfinder::Event::EventManager



Manager for PathfinderEvent handlers.  [More...](#detailed-description)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[AddHandler](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#function-addhandler)**(Type pathfinderEvent, MethodInfo handler, [EventHandlerOptions](../Classes/struct_pathfinder_1_1_event_1_1_event_handler_options/) options =default) =default<br>USE IS HEAVILY DISCOURAGED! Use the generic EventManager class instead unless you absolutely need to evaluate the type at runtime.  |
| void | **[AddHandler](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#function-addhandler)**(Action< T > handler, [EventHandlerOptions](../Classes/struct_pathfinder_1_1_event_1_1_event_handler_options/) options =default) =default<br>Adds an event handler, optionally with custom settings.  |
| void | **[RemoveHandler](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#function-removehandler)**(Action< T > handler, Assembly eventAssembly =null)<br>Removes a handler based on the handler method and its containing assembly.  |
| T | **[InvokeAll](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#function-invokeall)**(T eventArgs) |
| T | **[InvokeAssembly](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#function-invokeassembly)**(Assembly asm, T eventArgs) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| [EventManager](../Classes/class_pathfinder_1_1_event_1_1_event_manager/)< T > | **[Instance](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#property-instance)**  |
| int | **[HandlerCount](../Classes/class_pathfinder_1_1_event_1_1_event_manager/#property-handlercount)** <br>Number of event handlers attached to this event type.  |

## Detailed Description

```csharp
template <T >
class Pathfinder::Event::EventManager;
```

Manager for PathfinderEvent handlers. 

**Template Parameters**: 

  * **T** The type of PathfinderEvent

## Public Functions Documentation

### function AddHandler

```csharp
static void AddHandler(
    Type pathfinderEvent,
    MethodInfo handler,
    EventHandlerOptions options =default
) =default
```

USE IS HEAVILY DISCOURAGED! Use the generic EventManager class instead unless you absolutely need to evaluate the type at runtime. 

**Parameters**: 

  * **pathfinderEvent** The type of event to subscribe to, must inherit from PathfinderEvent>
  * **handler** MethodInfo of the handler method
  * **options** Options to use for the handler


**Exceptions**: 

  * **ArgumentException** 


### function AddHandler

```csharp
static void AddHandler(
    Action< T > handler,
    EventHandlerOptions options =default
) =default
```

Adds an event handler, optionally with custom settings. 

**Parameters**: 

  * **handler** The event handler to add
  * **options** Options to use with the handler


### function RemoveHandler

```csharp
static void RemoveHandler(
    Action< T > handler,
    Assembly eventAssembly =null
)
```

Removes a handler based on the handler method and its containing assembly. 

**Parameters**: 

  * **handler** Handler method for the event
  * **eventAssembly** Assembly associated with the event, by default the calling assembly


### function InvokeAll

```csharp
static T InvokeAll(
    T eventArgs
)
```


### function InvokeAssembly

```csharp
static T InvokeAssembly(
    Assembly asm,
    T eventArgs
)
```


## Public Property Documentation

### property Instance

```csharp
static EventManager< T > Instance;
```


### property HandlerCount

```csharp
static int HandlerCount;
```

Number of event handlers attached to this event type. 

-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000