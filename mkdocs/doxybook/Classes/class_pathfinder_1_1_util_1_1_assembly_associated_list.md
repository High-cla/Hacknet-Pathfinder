---
title: Pathfinder::Util::AssemblyAssociatedList

---

# Pathfinder::Util::AssemblyAssociatedList



 [More...](#detailed-description)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[Add](../Classes/class_pathfinder_1_1_util_1_1_assembly_associated_list/#function-add)**(T val, Assembly owner) |
| void | **[Remove](../Classes/class_pathfinder_1_1_util_1_1_assembly_associated_list/#function-remove)**(T val, Assembly owner) |
| void | **[RemoveAll](../Classes/class_pathfinder_1_1_util_1_1_assembly_associated_list/#function-removeall)**(Predicate< T > predicate, Assembly owner) |
| bool | **[RemoveAssembly](../Classes/class_pathfinder_1_1_util_1_1_assembly_associated_list/#function-removeassembly)**(Assembly asm, out List< T > removed) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| ReadOnlyCollection< T > | **[AllItems](../Classes/class_pathfinder_1_1_util_1_1_assembly_associated_list/#property-allitems)**  |
| ReadOnlyCollection< T > | **[this[Assembly assembly]](../Classes/class_pathfinder_1_1_util_1_1_assembly_associated_list/#property-this[assembly-assembly])**  |

## Detailed Description

```csharp
template <T >
class Pathfinder::Util::AssemblyAssociatedList;
```

## Public Functions Documentation

### function Add

```csharp
void Add(
    T val,
    Assembly owner
)
```


### function Remove

```csharp
void Remove(
    T val,
    Assembly owner
)
```


### function RemoveAll

```csharp
void RemoveAll(
    Predicate< T > predicate,
    Assembly owner
)
```


### function RemoveAssembly

```csharp
bool RemoveAssembly(
    Assembly asm,
    out List< T > removed
)
```


## Public Property Documentation

### property AllItems

```csharp
ReadOnlyCollection< T > AllItems;
```


### property this[Assembly assembly]

```csharp
ReadOnlyCollection< T > this[Assembly assembly];
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000