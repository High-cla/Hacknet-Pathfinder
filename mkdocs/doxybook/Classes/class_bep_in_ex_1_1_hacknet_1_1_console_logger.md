---
title: BepInEx::Hacknet::ConsoleLogger

---

# BepInEx::Hacknet::ConsoleLogger





Inherits from ILogListener

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[Dispose](../Classes/class_bep_in_ex_1_1_hacknet_1_1_console_logger/#function-dispose)**() |
| void | **[LogEvent](../Classes/class_bep_in_ex_1_1_hacknet_1_1_console_logger/#function-logevent)**(object sender, LogEventArgs eventArgs) |

## Protected Attributes

|                | Name           |
| -------------- | -------------- |
| readonly ConfigEntry< LogLevel > | **[ConfigConsoleDisplayedLevel](../Classes/class_bep_in_ex_1_1_hacknet_1_1_console_logger/#variable-configconsoledisplayedlevel)**  |
| readonly ConfigEntry< bool > | **[BackupConsoleEnabled](../Classes/class_bep_in_ex_1_1_hacknet_1_1_console_logger/#variable-backupconsoleenabled)**  |

## Public Functions Documentation

### function Dispose

```csharp
void Dispose()
```


### function LogEvent

```csharp
void LogEvent(
    object sender,
    LogEventArgs eventArgs
)
```


## Protected Attributes Documentation

### variable ConfigConsoleDisplayedLevel

```csharp
static readonly ConfigEntry< LogLevel > ConfigConsoleDisplayedLevel = ConfigFile.CoreConfig.Bind(
        "Logging.Console", "LogLevels",
        LogLevel.Fatal | LogLevel.Error | LogLevel.Warning | LogLevel.Message | LogLevel.Info,
        "Only displays the specified log levels in the console output.");
```


### variable BackupConsoleEnabled

```csharp
static readonly ConfigEntry< bool > BackupConsoleEnabled = ConfigFile.CoreConfig.Bind(
        "Logging.Console", "BackupConsole",
        false,
        "Enables backup console output in case the normal one fails.");
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000