---
title: Pathfinder::Event::Menu::DrawMainMenuButtonEvent

---

# Pathfinder::Event::Menu::DrawMainMenuButtonEvent





Inherits from [Pathfinder.Event.Menu.MainMenuEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/), [Pathfinder.Event.PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)

## Public Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ButtonData](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_button_event_1_1_button_data/)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[DrawMainMenuButtonEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_button_event/#function-drawmainmenubuttonevent)**([MainMenu](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/#property-mainmenu) mainMenu, [ButtonData](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_button_event_1_1_button_data/) data) |
| bool | **[ButtonDrawExecution](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_button_event/#function-buttondrawexecution)**(int id, int x, int y, int width, int height, string text, Color color, [MainMenu](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/#property-mainmenu) self, ref int yPosIndexOne, ref int yPostIndexTwo) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| [ButtonData](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_button_event_1_1_button_data/) | **[Data](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_draw_main_menu_button_event/#property-data)**  |

## Additional inherited members

**Public Functions inherited from [Pathfinder.Event.Menu.MainMenuEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/)**

|                | Name           |
| -------------- | -------------- |
| | **[MainMenuEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/#function-mainmenuevent)**([MainMenu](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/#property-mainmenu) mainMenu) |

**Public Properties inherited from [Pathfinder.Event.Menu.MainMenuEvent](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/)**

|                | Name           |
| -------------- | -------------- |
| MainMenu | **[MainMenu](../Classes/class_pathfinder_1_1_event_1_1_menu_1_1_main_menu_event/#property-mainmenu)**  |

**Public Properties inherited from [Pathfinder.Event.PathfinderEvent](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/)**

|                | Name           |
| -------------- | -------------- |
| bool | **[Cancelled](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/#property-cancelled)**  |
| bool | **[Thrown](../Classes/class_pathfinder_1_1_event_1_1_pathfinder_event/#property-thrown)**  |


## Public Functions Documentation

### function DrawMainMenuButtonEvent

```csharp
DrawMainMenuButtonEvent(
    MainMenu mainMenu,
    ButtonData data
)
```


### function ButtonDrawExecution

```csharp
static bool ButtonDrawExecution(
    int id,
    int x,
    int y,
    int width,
    int height,
    string text,
    Color color,
    MainMenu self,
    ref int yPosIndexOne,
    ref int yPostIndexTwo
)
```


## Public Property Documentation

### property Data

```csharp
ButtonData Data;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000