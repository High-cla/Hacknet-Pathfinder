---
title: Pathfinder::Util::FixedSizeCacheDict

---

# Pathfinder::Util::FixedSizeCacheDict



 [More...](#detailed-description)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[FixedSizeCacheDict](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/#function-fixedsizecachedict)**(int maxSize) |
| void | **[Register](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/#function-register)**(K key, V item) |
| bool | **[TryGetCached](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/#function-trygetcached)**(K key, out V val) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| [LRUCacheLinkedListNode](../Classes/class_pathfinder_1_1_util_1_1_l_r_u_cache_linked_list_node/)< K, V > | **[BackingListHead](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/#property-backinglisthead)**  |
| [LRUCacheLinkedListNode](../Classes/class_pathfinder_1_1_util_1_1_l_r_u_cache_linked_list_node/)< K, V > | **[BackingListTail](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/#property-backinglisttail)**  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| readonly int | **[Max](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/#variable-max)**  |

## Detailed Description

```csharp
template <K ,
V >
class Pathfinder::Util::FixedSizeCacheDict;
```

## Public Functions Documentation

### function FixedSizeCacheDict

```csharp
FixedSizeCacheDict(
    int maxSize
)
```


### function Register

```csharp
void Register(
    K key,
    V item
)
```


### function TryGetCached

```csharp
bool TryGetCached(
    K key,
    out V val
)
```


## Public Property Documentation

### property BackingListHead

```csharp
LRUCacheLinkedListNode< K, V > BackingListHead = null;
```


### property BackingListTail

```csharp
LRUCacheLinkedListNode< K, V > BackingListTail = null;
```


## Public Attributes Documentation

### variable Max

```csharp
readonly int Max;
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000