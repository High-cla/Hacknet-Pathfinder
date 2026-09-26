---
title: Pathfinder::Util::ErrorHelper

---

# Pathfinder::Util::ErrorHelper





## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[ThrowNotInherit](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-thrownotinherit)**(this Type type, string typeRefName, Type parentType, string extra =null) |
| void | **[ThrowNotInherit< InheritT >](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-thrownotinherit<-inheritt->)**(this Type type, string typeRefName, string extra =null) |
| void | **[ThrowNoDefaultCtor](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-thrownodefaultctor)**(this Type type, string nameOf) |
| void | **[ThrowNull< T >](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-thrownull<-t->)**(this T check, string nameOf) |
| void | **[ThrowNull< T >](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-thrownull<-t->)**(this T check, string nameOf, string msg) |
| void | **[ThrowOutOfRange](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-throwoutofrange)**(this int check, string nameOf, int lowerLimit =int.MinValue, int upperLimit =int.MaxValue) |
| void | **[ThrowNotSameSizeAs](../Classes/class_pathfinder_1_1_util_1_1_error_helper/#function-thrownotsamesizeas)**(this ICollection left, string leftNameOf, ICollection right, string rightNameOf) |

## Public Functions Documentation

### function ThrowNotInherit

```csharp
static void ThrowNotInherit(
    this Type type,
    string typeRefName,
    Type parentType,
    string extra =null
)
```


### function ThrowNotInherit< InheritT >

```csharp
static void ThrowNotInherit< InheritT >(
    this Type type,
    string typeRefName,
    string extra =null
)
```


### function ThrowNoDefaultCtor

```csharp
static void ThrowNoDefaultCtor(
    this Type type,
    string nameOf
)
```


### function ThrowNull< T >

```csharp
static void ThrowNull< T >(
    this T check,
    string nameOf
)
```


### function ThrowNull< T >

```csharp
static void ThrowNull< T >(
    this T check,
    string nameOf,
    string msg
)
```


### function ThrowOutOfRange

```csharp
static void ThrowOutOfRange(
    this int check,
    string nameOf,
    int lowerLimit =int.MinValue,
    int upperLimit =int.MaxValue
)
```


### function ThrowNotSameSizeAs

```csharp
static void ThrowNotSameSizeAs(
    this ICollection left,
    string leftNameOf,
    ICollection right,
    string rightNameOf
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000