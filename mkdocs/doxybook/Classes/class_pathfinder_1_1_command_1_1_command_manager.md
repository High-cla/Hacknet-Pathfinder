---
title: Pathfinder::Command::CommandManager

---

# Pathfinder::Command::CommandManager





## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[RegisterCommand](../Classes/class_pathfinder_1_1_command_1_1_command_manager/#function-registercommand)**(string commandName, Action< OS, string[]> handler, bool addAutocomplete =true, bool caseSensitive =false) |
| void | **[UnregisterCommand](../Classes/class_pathfinder_1_1_command_1_1_command_manager/#function-unregistercommand)**(string commandName, Assembly pluginAsm =null) |

## Public Functions Documentation

### function RegisterCommand

```csharp
static void RegisterCommand(
    string commandName,
    Action< OS, string[]> handler,
    bool addAutocomplete =true,
    bool caseSensitive =false
)
```


### function UnregisterCommand

```csharp
static void UnregisterCommand(
    string commandName,
    Assembly pluginAsm =null
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000