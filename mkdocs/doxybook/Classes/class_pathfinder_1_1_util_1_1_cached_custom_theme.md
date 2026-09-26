---
title: Pathfinder::Util::CachedCustomTheme

---

# Pathfinder::Util::CachedCustomTheme





Inherits from IDisposable

## Public Functions

|                | Name           |
| -------------- | -------------- |
| delegate ref Color | **[RefColorFieldDelegate](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#function-refcolorfielddelegate)**(OS instance) |
| | **[CachedCustomTheme](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#function-cachedcustomtheme)**(string themeFileName) |
| void | **[Load](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#function-load)**(bool isMainThread) |
| void | **[ApplyTo](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#function-applyto)**(OS os) |
| void | **[Dispose](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#function-dispose)**() |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| [ElementInfo](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_element_info/) | **[ThemeInfo](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#property-themeinfo)**  |
| Texture2D | **[BackgroundImage](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#property-backgroundimage)**  |
| string | **[Path](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#property-path)**  |
| bool | **[Loaded](../Classes/class_pathfinder_1_1_util_1_1_cached_custom_theme/#property-loaded)**  |

## Public Functions Documentation

### function RefColorFieldDelegate

```csharp
delegate ref Color RefColorFieldDelegate(
    OS instance
)
```


### function CachedCustomTheme

```csharp
CachedCustomTheme(
    string themeFileName
)
```


### function Load

```csharp
void Load(
    bool isMainThread
)
```


### function ApplyTo

```csharp
void ApplyTo(
    OS os
)
```


### function Dispose

```csharp
void Dispose()
```


## Public Property Documentation

### property ThemeInfo

```csharp
ElementInfo ThemeInfo;
```


### property BackgroundImage

```csharp
Texture2D BackgroundImage;
```


### property Path

```csharp
string Path;
```


### property Loaded

```csharp
bool Loaded = false;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000