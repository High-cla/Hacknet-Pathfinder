---
title: PathfinderAPI/Util/FixedSizeCacheDict.cs

---

# PathfinderAPI/Util/FixedSizeCacheDict.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Util](../Namespaces/namespace_pathfinder_1_1_util/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::LRUCacheLinkedListNode](../Classes/class_pathfinder_1_1_util_1_1_l_r_u_cache_linked_list_node/)**  |
| class | **[Pathfinder::Util::FixedSizeCacheDict](../Classes/class_pathfinder_1_1_util_1_1_fixed_size_cache_dict/)**  |




## Source code

```csharp
namespace Pathfinder.Util;

public class LRUCacheLinkedListNode<K,V> where K : class where V : class
{
    public K Key {get; set;} = default;
    public V Value {get; set;} = default;
    public LRUCacheLinkedListNode<K,V> Next {get; set;} = null;
    public LRUCacheLinkedListNode<K,V> Previous {get; set;} = null;
}

public class FixedSizeCacheDict<K, V> where K : class where V : class
{
    public readonly int Max;
    public LRUCacheLinkedListNode<K, V> BackingListHead { get; private set; } = null;
    public LRUCacheLinkedListNode<K,V> BackingListTail { get; private set; } = null;
    private readonly Dictionary<K, LRUCacheLinkedListNode<K,V>> FastAccessDict = new Dictionary<K, LRUCacheLinkedListNode<K,V>>();
        
    public FixedSizeCacheDict(int maxSize)
    {
        Max = maxSize;

        // List initialization
        if (maxSize != 0)
        {
            BackingListHead = new LRUCacheLinkedListNode<K,V>();
            var previousNode = BackingListHead;
            var currentNode = BackingListHead;
            for (int i = 1; i < maxSize; i++) {
                currentNode = new LRUCacheLinkedListNode<K,V>();
                previousNode.Next = currentNode;
                currentNode.Previous = previousNode;
                previousNode = currentNode;
            }
            BackingListTail = previousNode;
        }
    }

    private void touch(LRUCacheLinkedListNode<K,V> node)
    {
        // Stitch the end
        if (node.Next == null)
            BackingListTail = node.Previous;
        // Stitch the middle
        else
            node.Next.Previous = node.Previous;
        if (node.Previous != null)
            node.Previous.Next = node.Next;
        // Put in front
        node.Previous = null;
        node.Next = BackingListHead;
        BackingListHead.Previous = node;
        BackingListHead = node;
    }

    public void Register(K key, V item)
    {
        LRUCacheLinkedListNode<K,V> node;
        if (Max != 0)
        {
            // Eject last line of LRU Cache
            {
                var oldKey = BackingListTail.Key;
                if (oldKey != default)
                    FastAccessDict.Remove(oldKey);
                if (BackingListTail.Value is IDisposable disposable)
                    disposable.Dispose();
                BackingListTail.Value = default;
            }
            // Add new line
            {
                var current = BackingListTail;
                current.Key = key;
                current.Value = item;
                touch(current);
                node = current;
            }
        }
        else
        {
            node = new LRUCacheLinkedListNode<K,V>();
            node.Key = key;
            node.Value = item;
        }
        FastAccessDict.Add(key, node);
    }

    public bool TryGetCached(K key, out V val)
    {
        if (FastAccessDict.TryGetValue(key, out LRUCacheLinkedListNode<K,V> node))
        {
            if (Max != 0)
                touch(node);
            val = node.Value;
            return true;
        }

        val = default;
        return false;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
