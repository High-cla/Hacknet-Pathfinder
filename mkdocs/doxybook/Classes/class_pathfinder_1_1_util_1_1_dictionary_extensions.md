---
title: Pathfinder::Util::DictionaryExtensions

---

# Pathfinder::Util::DictionaryExtensions





## Public Functions

|                | Name           |
| -------------- | -------------- |
| string | **[GetString< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getstring<-key->)**(this Dictionary< Key, string > dict, Key key, string defaultVal ="") |
| string | **[GetOrThrow< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getorthrow<-key->)**(this Dictionary< Key, string > dict, Key key, string exMessage, Predicate< string > validator =null) |
| string | **[GetAnyOrThrow< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getanyorthrow<-key->)**(this Dictionary< Key, string > dict, Key[] keys, string exMessage, Predicate< string > validator =null) |
| string | **[GetOrWarn< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getorwarn<-key->)**(this Dictionary< Key, string > dict, Key key, string warnMessage, Predicate< string > validator =null) |
| TValue | **[GetOrDefault< TKey, TValue >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getordefault<-tkey,-tvalue->)**(this Dictionary< TKey, TValue > dict, TKey key) |
| int | **[GetInt< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getint<-key->)**(this Dictionary< Key, string > dict, Key key, int defaultVal =0) |
| bool | **[GetBool< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getbool<-key->)**(this Dictionary< Key, string > dict, Key key, bool defaultVal =false) |
| float | **[GetFloat< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getfloat<-key->)**(this Dictionary< Key, string > dict, Key key, float defaultVal =0f) |
| byte | **[GetByte< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getbyte<-key->)**(this Dictionary< Key, string > dict, Key key, byte defaultVal =0) |
| ? Vector2 | **[GetVector< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getvector<-key->)**(this Dictionary< Key, string > dict, Key x, Key y, Vector2? defaultVal =null) |
| ? Color | **[GetColor< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getcolor<-key->)**(this Dictionary< Key, string > dict, Key key, Color? defaultVal =null) |
| Computer | **[GetComp< Key >](../Classes/class_pathfinder_1_1_util_1_1_dictionary_extensions/#function-getcomp<-key->)**(this Dictionary< Key, string > dict, Key key, [SearchType](../Namespaces/namespace_pathfinder_1_1_util/#enum-searchtype) searchType =[SearchType.Any](../Namespaces/namespace_pathfinder_1_1_util/#enumvalue-any), string exMessage =null) |

## Public Functions Documentation

### function GetString< Key >

```csharp
static string GetString< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    string defaultVal =""
)
```


### function GetOrThrow< Key >

```csharp
static string GetOrThrow< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    string exMessage,
    Predicate< string > validator =null
)
```


### function GetAnyOrThrow< Key >

```csharp
static string GetAnyOrThrow< Key >(
    this Dictionary< Key, string > dict,
    Key[] keys,
    string exMessage,
    Predicate< string > validator =null
)
```


### function GetOrWarn< Key >

```csharp
static string GetOrWarn< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    string warnMessage,
    Predicate< string > validator =null
)
```


### function GetOrDefault< TKey, TValue >

```csharp
static TValue GetOrDefault< TKey, TValue >(
    this Dictionary< TKey, TValue > dict,
    TKey key
)
```


### function GetInt< Key >

```csharp
static int GetInt< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    int defaultVal =0
)
```


### function GetBool< Key >

```csharp
static bool GetBool< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    bool defaultVal =false
)
```


### function GetFloat< Key >

```csharp
static float GetFloat< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    float defaultVal =0f
)
```


### function GetByte< Key >

```csharp
static byte GetByte< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    byte defaultVal =0
)
```


### function GetVector< Key >

```csharp
static ? Vector2 GetVector< Key >(
    this Dictionary< Key, string > dict,
    Key x,
    Key y,
    Vector2? defaultVal =null
)
```


### function GetColor< Key >

```csharp
static ? Color GetColor< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    Color? defaultVal =null
)
```


### function GetComp< Key >

```csharp
static Computer GetComp< Key >(
    this Dictionary< Key, string > dict,
    Key key,
    SearchType searchType =SearchType.Any,
    string exMessage =null
)
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000