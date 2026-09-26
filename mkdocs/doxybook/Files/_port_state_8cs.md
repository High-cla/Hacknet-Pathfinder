---
title: PathfinderAPI/Port/PortState.cs

---

# PathfinderAPI/Port/PortState.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Port](../Namespaces/namespace_pathfinder_1_1_port/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Port::PortState](../Classes/class_pathfinder_1_1_port_1_1_port_state/)**  |




## Source code

```csharp
using Hacknet;

namespace Pathfinder.Port;

public class PortState
{
    public Computer Computer { get; internal set; }
    public PortRecord Record { get; }
    private string _DisplayName;
    public string DisplayName
    {
        get => _DisplayName;
        set => _DisplayName = value ?? Record.DefaultDisplayName;
    }
    private int _PortNumber;
    public int PortNumber
    {
        get => _PortNumber;
        set => _PortNumber = value  > -1 ? value : Record.DefaultPortNumber;
    }
    public bool Cracked { get; set; }
    public void SetCracked(bool cracked, string ipFrom)
    {
        if(cracked && !Cracked)
            Computer.openPort(Record.Protocol, ipFrom);
        else if(!cracked && Cracked)
            Computer.closePort(Record.Protocol, ipFrom);
    }

    public PortState(Computer comp, PortRecord record, bool cracked) : this(comp, record, null, cracked: cracked)
    {
    }
    public PortState(Computer comp, PortRecord record, string displayName = null, int portNumber = -1, bool cracked = false)
    {
        Computer = comp;
        Record = record;
        Cracked = cracked;
        DisplayName = displayName;
        PortNumber = portNumber;
    }
    public PortState(Computer comp, string protocol, bool cracked) : this(comp, protocol, null, cracked: cracked)
    {
    }
    public PortState(Computer comp, string protocol, string displayName = null, int portNumber = -1, bool cracked = false)
    {
        Computer = comp;
        Record = PortManager.GetPortRecordFromProtocol(protocol);
        Cracked = cracked;
        DisplayName = displayName;
        PortNumber = portNumber;
    }

    public PortState Clone(Computer comp = null)
    {
        return Record.CreateState(comp, _DisplayName, _PortNumber, Cracked);
    }

    public bool Remove()
    {
        return Computer.RemovePort(Record);
    }
        
#pragma warning disable 618
    [Obsolete("Avoid PortData")]
    public static explicit operator PortData(PortState state)
        => new PortData(state.Record.Protocol, state.Record.OriginalPortNumber, state.PortNumber, state.DisplayName)
        {
            Cracked = state.Cracked
        };

    [Obsolete("Avoid PortData")]
    public static explicit operator PortState(PortData data)
        => new PortState(null, (PortRecord)data, data.Cracked);
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
