---
title: PathfinderAPI/Event/Menu/MainMenuEvent.cs

---

# PathfinderAPI/Event/Menu/MainMenuEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Menu](../Namespaces/namespace_pathfinder_1_1_event_1_1_menu/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Menu::MainMenuEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/)**  |




## Source code

```csharp
using Hacknet;

namespace Pathfinder.Event.Menu;

public abstract class MainMenuEvent : PathfinderEvent
{
    public MainMenu MainMenu { get; private set; }
    public MainMenuEvent(MainMenu mainMenu) { MainMenu = mainMenu; }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
