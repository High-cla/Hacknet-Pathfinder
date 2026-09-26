---
title: PathfinderAPI/Meta/Load/CommandAttribute.cs

---

# PathfinderAPI/Meta/Load/CommandAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Meta](../Namespaces/namespace_pathfinder_1_1_meta/)**  |
| **[Pathfinder::Meta::Load](../Namespaces/namespace_pathfinder_1_1_meta_1_1_load/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Meta::Load::CommandAttribute](../Classes/class_pathfinder_1_1_meta_1_1_load_1_1_command_attribute/)**  |




## Source code

```csharp
using System.Reflection;
using BepInEx.Hacknet;
using Hacknet;
using Pathfinder.Command;

namespace Pathfinder.Meta.Load;

[AttributeUsage(AttributeTargets.Method, AllowMultiple = true)]
public class CommandAttribute : BaseAttribute
{
    public string CommandName { get; }
    public bool AddAutocomplete { get; set; }
    public bool CaseSensitive { get; set; }

    public CommandAttribute(string commandName, bool addAutocomplete = true, bool caseSensitive = false)
    {
        CommandName = commandName;
        AddAutocomplete = addAutocomplete;
        CaseSensitive = caseSensitive;
    }

    protected internal override void CallOn(HacknetPlugin plugin, MemberInfo targettedInfo)
    {
        var methodInfo = (MethodInfo)targettedInfo;
        var commandAction = (Action<OS, string[]>)methodInfo.CreateDelegate(typeof(Action<OS, string[]>));
        CommandManager.RegisterCommandInternal(CommandName, targettedInfo.Module.Assembly, commandAction, AddAutocomplete, CaseSensitive);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
