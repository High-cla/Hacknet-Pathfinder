---
title: PathfinderAPI/Executable/GameExecutable.cs

---

# PathfinderAPI/Executable/GameExecutable.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Executable](../Namespaces/namespace_pathfinder_1_1_executable/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Executable::GameExecutable](../Classes/class_pathfinder_1_1_executable_1_1_game_executable/)**  |




## Source code

```csharp
using Hacknet;
using Microsoft.Xna.Framework;

namespace Pathfinder.Executable;

public enum CompletionResult
{
    Error = -1,
    Running,
    Failure,
    Killed,
    Success,
}
public class GameExecutable : BaseExecutable
{
    public float Lifetime { get; set; }
    private CompletionResult _Result = CompletionResult.Running;
    public CompletionResult Result
    {
        get => _Result;
        set
        {
            _Result = value;
            isExiting = Result != CompletionResult.Running;
        }
    }
    public virtual bool CanAddToSystem { get; set; } = true;
    public virtual bool CanBeKilled { get; set; } = true;
    public virtual string ErrorReturn { get; set; }
    public virtual bool IgnoreProxyFailPrint { get; set; }
    public virtual bool IgnoreMemoryBehaviorPrint { get; set; }

    public GameExecutable() : base(default, OS.currentInstance, null)
    {
    }

    public void Assign(Rectangle location, OS os, string[] args)
    {
        this.os = os;
        bounds = location;
        Args = args;
    }

    public virtual void OnInitialize() {}

    public virtual void OnCompleteError() {}
    public virtual void OnCompleteFailure() {}
    public virtual void OnCompleteKilled() {}
    public virtual void OnCompleteSuccess() {}
    public virtual void OnComplete() {}

    public virtual void OnNoAvailableRam() {}
    public virtual void OnProxyBypassFailure() {}
    public virtual void OnUpdate(float delta) {}

    public virtual bool CatchException(Exception exception) { return false; }

    public sealed override void LoadContent() {}

    public sealed override void Completed()
    {
        try
        {
            switch(Result)
            {
                case CompletionResult.Success:
                    OnCompleteSuccess();
                    break;
                case CompletionResult.Failure:
                    OnCompleteFailure();
                    break;
                case CompletionResult.Killed:
                    OnCompleteKilled();
                    break;
                case CompletionResult.Error:
                    OnCompleteError();
                    break;
            }
            OnComplete();

            if(Result == CompletionResult.Failure
               || Result == CompletionResult.Error
               && ErrorReturn != null)
                os.write($"{Args[0]}: {(Result == CompletionResult.Failure ? $"failed" : "errored")} with '{ErrorReturn}'");
        }
        catch(Exception e)
        {
            if(!CatchException(e))
                throw e;
        }
    }

    public sealed override void Killed()
    {
        Result = CompletionResult.Killed;
        needsRemoval = true;
        Completed();
    }

    public override void Update(float t)
    {
        base.Update(t);
        if(Result != CompletionResult.Running) return;
        Lifetime += t;
        try
        {
            OnUpdate(t);
        }
        catch(Exception e)
        {
            if(!CatchException(e))
                throw e;
        }
    }

    [Obsolete]
    public sealed override string GetIdentifier()
    {
        throw new NotImplementedException();
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
