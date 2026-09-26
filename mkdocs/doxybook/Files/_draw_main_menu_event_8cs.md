---
title: PathfinderAPI/Event/Menu/DrawMainMenuEvent.cs

---

# PathfinderAPI/Event/Menu/DrawMainMenuEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Menu](../Namespaces/namespace_pathfinder_1_1_event_1_1_menu/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Menu::DrawMainMenuEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_event/)**  |




## Source code

```csharp
using Hacknet;
using HarmonyLib;
using Mono.Cecil.Cil;
using MonoMod.Cil;

namespace Pathfinder.Event.Menu;

[HarmonyPatch]
public class DrawMainMenuEvent : MainMenuEvent
{
    public DrawMainMenuEvent(MainMenu mainMenu) : base(mainMenu)
    {
    }

    [HarmonyILManipulator]
    [HarmonyPatch(typeof(MainMenu), nameof(MainMenu.Draw))]
    private static void AfterMainMenuDraw(ILContext il)
    {
        ILCursor c = new ILCursor(il);

        c.GotoNext(MoveType.AfterLabel,
            x => x.MatchCallOrCallvirt(typeof(GuiData), nameof(GuiData.endDraw))
        );

        c.Emit(OpCodes.Ldarg_0);
        c.Emit(OpCodes.Newobj, AccessTools.DeclaredConstructor(typeof(DrawMainMenuEvent), new Type[] { typeof(MainMenu) }));
        c.Emit(OpCodes.Call, AccessTools.DeclaredMethod(typeof(EventManager<DrawMainMenuEvent>), nameof(EventManager<DrawMainMenuEvent>.InvokeAll)));
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
