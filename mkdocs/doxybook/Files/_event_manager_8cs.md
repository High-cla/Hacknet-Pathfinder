---
title: PathfinderAPI/Event/EventManager.cs

---

# PathfinderAPI/Event/EventManager.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Pathfinder::Event::EventHandlerOptions](../Classes/struct_pathfinder_1_1_event_1_1_event_handler_options/)**  |
| class | **[Pathfinder::Event::EventManager](../Classes/class_pathfinder_1_1_event_1_1_event_manager/)** <br>Manager for PathfinderEvent handlers.  |




## Source code

```csharp
using System.Reflection;
using HarmonyLib;
using System.Runtime.CompilerServices;
using Pathfinder.Util;

namespace Pathfinder.Event;

public struct EventHandlerOptions
{
    public int? Priority;
    public int PrioritySafe => Priority.GetValueOrDefault(0);
    public bool ContinueOnCancel;
    public bool ContinueOnThrow;
}
    
internal class EventHandler<T> : IComparable<EventHandler<T>>, IEquatable<EventHandler<T>>, IEquatable<MethodInfo> where T : PathfinderEvent
{
    internal readonly Action<T> HandlerAction;
    internal readonly MethodInfo HandlerInfo;
    internal readonly EventHandlerOptions Options;

    internal EventHandler(Action<T> handlerAction, EventHandlerOptions options)
    {
        HandlerAction = handlerAction;
        Options = options;

        HandlerInfo = handlerAction.Method;
    }

    public int CompareTo(EventHandler<T> other) => Options.PrioritySafe.CompareTo(other.Options.PrioritySafe);

    public bool Equals(EventHandler<T> other) => HandlerInfo.Equals(other?.HandlerInfo);

    public bool Equals(MethodInfo other) => HandlerInfo.Equals(other);
}
    
public static class EventManager
{
    internal static readonly List<object> Instances = new List<object>();
    internal static void AddEventManagerInstance(object managerObj)
    {
        Instances.Add(managerObj);
    }
    internal delegate void RemoveOnUnload(Assembly unloadedAssembly);
    internal static event RemoveOnUnload onPluginUnload;
    internal static void InvokeOnPluginUnload(Assembly pluginAsm) => onPluginUnload?.Invoke(pluginAsm);

    [MethodImpl(MethodImplOptions.NoInlining)]
    public static void AddHandler(Type pathfinderEvent, MethodInfo handler, EventHandlerOptions options = default)
    {
        pathfinderEvent.ThrowNotInherit<PathfinderEvent>(nameof(pathfinderEvent));
        var parameters = handler.GetParameters();
        if (parameters.Length != 1 || parameters[0].ParameterType != pathfinderEvent)
        {
            throw new ArgumentException("Handler method must have one parameter of the same type of event you're subscribing to!", nameof(handler));
        }

        object handlerDelegate = typeof(AccessTools)
            .GetMethod("MethodDelegate")
            .MakeGenericMethod(typeof(Action<>).MakeGenericType(pathfinderEvent))
            .Invoke(null, new object[] { handler, null, true });

        object eventHandler = Activator.CreateInstance(
            typeof(EventHandler<>).MakeGenericType(pathfinderEvent),
            AccessTools.all,
            default,
            new object[] { handlerDelegate, options },
            default
        );

        var eventManagerType = typeof(EventManager<>).MakeGenericType(pathfinderEvent);

        object instance = eventManagerType.GetProperty("Instance").GetGetMethod().Invoke(null, null);
            
        eventManagerType
            .GetMethod("AddHandlerInternal", AccessTools.all)
            .Invoke(instance, new object[] { eventHandler, handler.Module.Assembly });
    }
}

public class EventManager<T> where T : PathfinderEvent
{
    private readonly AssemblyAssociatedList<EventHandler<T>> handlers = new AssemblyAssociatedList<EventHandler<T>>();

    private static EventManager<T> _instance = null;

    public static EventManager<T> Instance => _instance ?? (_instance = new EventManager<T>());

    private EventManager()
    {
        EventManager.AddEventManagerInstance(this);
        EventManager.onPluginUnload += OnPluginUnload;
    }
        
    [MethodImpl(MethodImplOptions.NoInlining)]
    public static void AddHandler(Action<T> handler, EventHandlerOptions options = default)
    {
        Instance.AddHandlerInternal(new EventHandler<T>(handler, options), Assembly.GetCallingAssembly());
    }
    private void AddHandlerInternal(EventHandler<T> handler, Assembly eventAssembly)
    {
        handlers.Add(handler, eventAssembly);
    }

    [MethodImpl(MethodImplOptions.NoInlining)]
    public static void RemoveHandler(Action<T> handler, Assembly eventAssembly = null)
    {
        Instance.RemoveHandlerInternal(handler.Method, eventAssembly ?? Assembly.GetCallingAssembly());
    }
    private void RemoveHandlerInternal(MethodInfo handler, Assembly eventAssembly)
    {
        handlers.RemoveAll(x => x.Equals(handler), eventAssembly);
    }

    public static int HandlerCount => Instance.handlers.AllItems.Count;

    private void OnPluginUnload(Assembly pluginAsm)
    {
        handlers.RemoveAssembly(pluginAsm, out _);
    }

    private static T InvokeOn(IEnumerable<EventHandler<T>> list, T eventArgs)
    {
        foreach (var handler in list)
        {
            try
            {
                if ((handler.Options.ContinueOnThrow || !eventArgs.Thrown) && (handler.Options.ContinueOnCancel || !eventArgs.Cancelled))
                    handler.HandlerAction(eventArgs);
            }
            catch (Exception e)
            {
                Logger.Log(global::BepInEx.Logging.LogLevel.Error, $"{handler.HandlerInfo.DeclaringType.FullName}::{handler.HandlerInfo.FullDescription()}");
                Logger.Log(global::BepInEx.Logging.LogLevel.Error, e);
                eventArgs.Thrown = true;
            }
        }
        return eventArgs;
    }

    public static T InvokeAll(T eventArgs)
    {
        var allHandlers = Instance.handlers.AllItems.ToList();
        allHandlers.Sort();
        return InvokeOn(allHandlers, eventArgs);
    }

    public static T InvokeAssembly(Assembly asm, T eventArgs)
    {
        var asmHandlers = Instance.handlers[asm].ToList();
        asmHandlers.Sort();
        return InvokeOn(asmHandlers, eventArgs);
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
