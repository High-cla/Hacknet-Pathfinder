---
title: Pathfinder::Executable::GameExecutable

---

# Pathfinder::Executable::GameExecutable





Inherits from [Pathfinder.Executable.BaseExecutable](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/), ExeModule

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[GameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-gameexecutable)**() |
| void | **[Assign](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-assign)**(Rectangle location, OS os, string[] args) |
| virtual void | **[OnInitialize](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-oninitialize)**()<br>Called immediately before being added to OS.exes.  |
| virtual void | **[OnCompleteError](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-oncompleteerror)**()<br>Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Error.  |
| virtual void | **[OnCompleteFailure](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-oncompletefailure)**()<br>Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Failure.  |
| virtual void | **[OnCompleteKilled](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-oncompletekilled)**()<br>Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Killed.  |
| virtual void | **[OnCompleteSuccess](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-oncompletesuccess)**()<br>Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Success.  |
| virtual void | **[OnComplete](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-oncomplete)**()<br>Called immediately before being removed from OS.exes. Called after any dedicated completion method.  |
| virtual void | **[OnNoAvailableRam](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-onnoavailableram)**()<br>Called when not enough ram is available to run the executable.  |
| virtual void | **[OnProxyBypassFailure](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-onproxybypassfailure)**()<br>Called when the computer has an active proxy and the executable could not bypass it.  |
| virtual void | **[OnUpdate](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-onupdate)**(float delta)<br>Called every Update when Result is CompletitionResult.Running.  |
| virtual bool | **[CatchException](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-catchexception)**(Exception exception)<br>Called when an exception in thrown for this executable.  |
| override void | **[LoadContent](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-loadcontent)**() |
| override void | **[Completed](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-completed)**() |
| override void | **[Killed](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-killed)**() |
| override void | **[Update](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-update)**(float t) |
| virtual override string | **[GetIdentifier](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#function-getidentifier)**() |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| float | **[Lifetime](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-lifetime)** <br>Lifetime value of the executable, added to upon being added to the OS on every Update.  |
| [CompletionResult](../Namespaces/namespace_pathfinder_1_1_executable/#enum-completionresult) | **[Result](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-result)** <br>Status of the executable, sets isExiting if not set to CompletionResult.Running.  |
| bool | **[CanAddToSystem](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-canaddtosystem)** <br>Determines whether the executable is added to the OS when executed.  |
| bool | **[CanBeKilled](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-canbekilled)** <br>Determines whether the executable can be killed.  |
| string | **[ErrorReturn](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-errorreturn)** <br>Written to the terminal if failed or errored when not null.  |
| bool | **[IgnoreProxyFailPrint](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-ignoreproxyfailprint)** <br>Determines whether the vanilla proxy fail behavior should also happen.  |
| bool | **[IgnoreMemoryBehaviorPrint](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/#property-ignorememorybehaviorprint)** <br>Determines whether the vanilla no available memory fail behavior should also happen.  |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Executable.BaseExecutable](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/)**

|                | Name           |
| -------------- | -------------- |
| | **[BaseExecutable](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/#function-baseexecutable)**(Rectangle location, OS operatingSystem, string[] args) |

**Public Attributes inherited from [Pathfinder.Executable.BaseExecutable](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/)**

|                | Name           |
| -------------- | -------------- |
| string[] | **[Args](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/#variable-args)**  |


## Public Functions Documentation

### function GameExecutable

```csharp
GameExecutable()
```


### function Assign

```csharp
void Assign(
    Rectangle location,
    OS os,
    string[] args
)
```


### function OnInitialize

```csharp
virtual void OnInitialize()
```

Called immediately before being added to OS.exes. 

### function OnCompleteError

```csharp
virtual void OnCompleteError()
```

Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Error. 

### function OnCompleteFailure

```csharp
virtual void OnCompleteFailure()
```

Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Failure. 

### function OnCompleteKilled

```csharp
virtual void OnCompleteKilled()
```

Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Killed. 

### function OnCompleteSuccess

```csharp
virtual void OnCompleteSuccess()
```

Called immediately before being removed from OS.exes. Called when Result is CompletionResult.Success. 

### function OnComplete

```csharp
virtual void OnComplete()
```

Called immediately before being removed from OS.exes. Called after any dedicated completion method. 

### function OnNoAvailableRam

```csharp
virtual void OnNoAvailableRam()
```

Called when not enough ram is available to run the executable. 

### function OnProxyBypassFailure

```csharp
virtual void OnProxyBypassFailure()
```

Called when the computer has an active proxy and the executable could not bypass it. 

### function OnUpdate

```csharp
virtual void OnUpdate(
    float delta
)
```

Called every Update when Result is CompletitionResult.Running. 

**Parameters**: 

  * **delta** The time since the last OS.Update call


### function CatchException

```csharp
virtual bool CatchException(
    Exception exception
)
```

Called when an exception in thrown for this executable. 

**Parameters**: 

  * **exception** The thrown exception


**Return**: True if the exception is caught, false if it propagates

### function LoadContent

```csharp
override void LoadContent()
```


### function Completed

```csharp
override void Completed()
```


### function Killed

```csharp
override void Killed()
```


### function Update

```csharp
override void Update(
    float t
)
```


### function GetIdentifier

```csharp
virtual override string GetIdentifier()
```


**Reimplements**: [Pathfinder::Executable::BaseExecutable::GetIdentifier](../Classes/class_pathfinder_1_1_executable_1_1_base_executable/#function-getidentifier)


## Public Property Documentation

### property Lifetime

```csharp
float Lifetime;
```

Lifetime value of the executable, added to upon being added to the OS on every Update. 

### property Result

```csharp
CompletionResult Result;
```

Status of the executable, sets isExiting if not set to CompletionResult.Running. 

### property CanAddToSystem

```csharp
bool CanAddToSystem = true;
```

Determines whether the executable is added to the OS when executed. 

### property CanBeKilled

```csharp
bool CanBeKilled = true;
```

Determines whether the executable can be killed. 

### property ErrorReturn

```csharp
string ErrorReturn;
```

Written to the terminal if failed or errored when not null. 

### property IgnoreProxyFailPrint

```csharp
bool IgnoreProxyFailPrint;
```

Determines whether the vanilla proxy fail behavior should also happen. 

### property IgnoreMemoryBehaviorPrint

```csharp
bool IgnoreMemoryBehaviorPrint;
```

Determines whether the vanilla no available memory fail behavior should also happen. 

-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000