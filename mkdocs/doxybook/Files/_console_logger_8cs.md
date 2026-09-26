---
title: BepInEx.Hacknet/ConsoleLogger.cs

---

# BepInEx.Hacknet/ConsoleLogger.cs



## Namespaces

| Name           |
| -------------- |
| **[BepInEx](../Namespaces/namespace_bep_in_ex/)**  |
| **[BepInEx::Hacknet](../Namespaces/namespace_bep_in_ex_1_1_hacknet/)**  |
| **[BepInEx::Logging](../Namespaces/namespace_bep_in_ex_1_1_logging/)**  |
| **[BepInEx::Configuration](../Namespaces/namespace_bep_in_ex_1_1_configuration/)**  |




## Source code

```csharp
using BepInEx.Logging;
using BepInEx.Configuration;

namespace BepInEx.Hacknet;

internal class ConsoleLogger : ILogListener
{
    protected static readonly ConfigEntry<LogLevel> ConfigConsoleDisplayedLevel = ConfigFile.CoreConfig.Bind(
        "Logging.Console", "LogLevels",
        LogLevel.Fatal | LogLevel.Error | LogLevel.Warning | LogLevel.Message | LogLevel.Info,
        "Only displays the specified log levels in the console output.");

    protected static readonly ConfigEntry<bool> BackupConsoleEnabled = ConfigFile.CoreConfig.Bind(
        "Logging.Console", "BackupConsole",
        false,
        "Enables backup console output in case the normal one fails.");

    public void Dispose() { }

    public void LogEvent(object sender, LogEventArgs eventArgs)
    {
        if (!BackupConsoleEnabled.Value || (eventArgs.Level & ConfigConsoleDisplayedLevel.Value) == 0)
            return;

        Console.ForegroundColor = eventArgs.Level.GetConsoleColor();
        Console.Out.Write(eventArgs.ToStringLine());
        Console.ForegroundColor = ConsoleColor.Gray;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
