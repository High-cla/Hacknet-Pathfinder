---
title: PathfinderAPI/Event/Loading/TextReplaceEvent.cs

---

# PathfinderAPI/Event/Loading/TextReplaceEvent.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Event](../Namespaces/namespace_pathfinder_1_1_event/)**  |
| **[Pathfinder::Event::Loading](../Namespaces/namespace_pathfinder_1_1_event_1_1_loading/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Event::Loading::TextReplaceEvent](../Classes/class_pathfinder_1_1_event_1_1_loading_1_1_text_replace_event/)**  |




## Source code

```csharp
using HarmonyLib;
using Hacknet;

namespace Pathfinder.Event.Loading;

[HarmonyPatch]
public class TextReplaceEvent : PathfinderEvent
{
    public string Original { get; }
    public string Replacement { get; set; }

    public TextReplaceEvent(string original, string replacement)
    {
        Original = original;
        Replacement = replacement;
    }

    [HarmonyPostfix]
    [HarmonyPatch(typeof(ComputerLoader), nameof(ComputerLoader.filter))]
    private static void TextFilterPostfix(ref string s, ref string __result)
    {
        var textReplaceEvent = new TextReplaceEvent(s, __result);
        EventManager<TextReplaceEvent>.InvokeAll(textReplaceEvent);
        __result = textReplaceEvent.Replacement;
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
