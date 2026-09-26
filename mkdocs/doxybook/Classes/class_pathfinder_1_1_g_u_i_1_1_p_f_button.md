---
title: Pathfinder::GUI::PFButton

---

# Pathfinder::GUI::PFButton





Inherits from IDisposable

## Public Functions

|                | Name           |
| -------------- | -------------- |
| int | **[GetNextID](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-getnextid)**() |
| void | **[ReturnID](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-returnid)**(int id) |
| | **[PFButton](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-pfbutton)**(int x, int y, int width, int height, string text, [Color](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-color)? color =null, Texture2D texture =null) |
| bool | **[Do](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-do)**() |
| bool | **[Do](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-do)**(Point offset) |
| bool | **[Do](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-do)**(Rectangle offset) |
| bool | **[Do](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-do)**(Vector2 offset) |
| bool | **[Do](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-do)**(int offsetX, int offsetY) |
| void | **[Dispose](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#function-dispose)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| readonly int | **[ID](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-id)**  |
| int | **[X](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-x)**  |
| int | **[Y](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-y)**  |
| int | **[Height](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-height)**  |
| int | **[Width](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-width)**  |
| string | **[Text](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-text)**  |
| Color? | **[Color](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-color)**  |
| Texture2D | **[Texture](../Classes/class_pathfinder_1_1_g_u_i_1_1_p_f_button/#variable-texture)**  |

## Public Functions Documentation

### function GetNextID

```csharp
static int GetNextID()
```


### function ReturnID

```csharp
static void ReturnID(
    int id
)
```


### function PFButton

```csharp
PFButton(
    int x,
    int y,
    int width,
    int height,
    string text,
    Color? color =null,
    Texture2D texture =null
)
```


### function Do

```csharp
bool Do()
```


### function Do

```csharp
bool Do(
    Point offset
)
```


### function Do

```csharp
bool Do(
    Rectangle offset
)
```


### function Do

```csharp
bool Do(
    Vector2 offset
)
```


### function Do

```csharp
bool Do(
    int offsetX,
    int offsetY
)
```


### function Dispose

```csharp
void Dispose()
```


## Public Attributes Documentation

### variable ID

```csharp
readonly int ID = GetNextID();
```


### variable X

```csharp
int X;
```


### variable Y

```csharp
int Y;
```


### variable Height

```csharp
int Height;
```


### variable Width

```csharp
int Width;
```


### variable Text

```csharp
string Text;
```


### variable Color

```csharp
Color? Color;
```


### variable Texture

```csharp
Texture2D Texture;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000