---
title: Pathfinder::Replacements::ObjectSerializerReplacement

---

# Pathfinder::Replacements::ObjectSerializerReplacement





## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[SerializeObject](../Classes/class_pathfinder_1_1_replacements_1_1_object_serializer_replacement/#function-serializeobject)**(object o, bool preventOuterTag, ref string __result) |
| bool | **[DeserializeObject](../Classes/class_pathfinder_1_1_replacements_1_1_object_serializer_replacement/#function-deserializeobject)**(XmlReader rdr, Type t, out object __result) |
| bool | **[GetRenderablesFromTypePrefix](../Classes/class_pathfinder_1_1_replacements_1_1_object_serializer_replacement/#function-getrenderablesfromtypeprefix)**(Type type, object o, int indentLevel, ref List< ReflectiveRenderer.RenderableField > __result) |

## Public Functions Documentation

### function SerializeObject

```csharp
static bool SerializeObject(
    object o,
    bool preventOuterTag,
    ref string __result
)
```


### function DeserializeObject

```csharp
static bool DeserializeObject(
    XmlReader rdr,
    Type t,
    out object __result
)
```


### function GetRenderablesFromTypePrefix

```csharp
static bool GetRenderablesFromTypePrefix(
    Type type,
    object o,
    int indentLevel,
    ref List< ReflectiveRenderer.RenderableField > __result
)
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000