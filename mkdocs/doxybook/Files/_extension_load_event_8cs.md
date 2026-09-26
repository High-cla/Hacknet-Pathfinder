---
title: PathfinderAPI/Event/Loading/ExtensionLoadEvent.cs

---

# PathfinderAPI/Event/Loading/ExtensionLoadEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Loading](../Namespaces/namespace_pathfinder_1_1_event_1_1_loading/)**  |
| **[Hacknet::Gui](../Namespaces/namespace_hacknet_1_1_gui/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Loading::ExtensionLoadEvent](../Classes/class_pathfinder_1_1_event_1_1_loading_1_1_extension_load_event/)**  |




## Source code

```csharp
using Hacknet;
using Hacknet.Extensions;
using Hacknet.Gui;
using Hacknet.Screens;
using HarmonyLib;
using Microsoft.Xna.Framework;

namespace Pathfinder.Event.Loading;

[HarmonyPatch]
public class ExtensionLoadEvent : PathfinderEvent
{
    public ExtensionInfo Info { get; }
    public bool Unload { get; }

    public ExtensionLoadEvent(ExtensionInfo info, bool unload)
    {
        Info = info;
        Unload = unload;
    }

    [HarmonyPostfix]
    [HarmonyPatch(typeof(ExtensionsMenuScreen), nameof(ExtensionsMenuScreen.ActivateExtensionPage))]
    internal static void ExtensionLoadPostfix(ExtensionInfo info)
    {
        var loadEvent = new ExtensionLoadEvent(info, false);
        EventManager<ExtensionLoadEvent>.InvokeAll(loadEvent);
    }

    [HarmonyPrefix]
    [HarmonyPatch(typeof(OS), nameof(OS.quitGame))]
    private static void OSQuitPrefix()
    {
        if (Settings.IsInExtensionMode)
        {
            var unloadEvent = new ExtensionLoadEvent(ExtensionLoader.ActiveExtensionInfo, true);
            EventManager<ExtensionLoadEvent>.InvokeAll(unloadEvent);
        }
    }

    // I would hook Hacknet.Screens.DrawExtensionInfoDetail instead, but for some reason that method is cursed, so I look here instead
    [HarmonyPostfix]
    [HarmonyPatch(typeof(Button), nameof(Button.doButton), new Type[] { typeof(int), typeof(int), typeof(int), typeof(int), typeof(int), typeof(string), typeof(Color?) })]
    [HarmonyBefore("BepInEx.Hacknet.Chainloader")]
    private static void OnBackButtonPressPostfix(int myID, bool __result)
    {
        if (myID == 7900040 && __result)
        {
            var unloadEvent = new ExtensionLoadEvent(ExtensionLoader.ActiveExtensionInfo, true);
            EventManager<ExtensionLoadEvent>.InvokeAll(unloadEvent);
        }
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
