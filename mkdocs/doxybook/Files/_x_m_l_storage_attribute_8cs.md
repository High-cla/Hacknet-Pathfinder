---
title: PathfinderAPI/Util/XMLStorageAttribute.cs

---

# PathfinderAPI/Util/XMLStorageAttribute.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Util](../Namespaces/namespace_pathfinder_1_1_util/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::XMLStorageAttribute](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_storage_attribute/)**  |
| interface | **[Pathfinder::Util::IXmlName](../Classes/interface_pathfinder_1_1_util_1_1_i_xml_name/)**  |




## Source code

```csharp
using System.Reflection;
using System.Xml.Linq;
using BepInEx.Logging;
using Pathfinder.Util.XML;

namespace Pathfinder.Util;

[AttributeUsage(AttributeTargets.Field | AttributeTargets.Property, AllowMultiple = false)]
public class XMLStorageAttribute : Attribute
{
    public bool IsContent { get; set; } = false;
    public Type Converter { get; set; } = null;
        
    private const BindingFlags Flags = BindingFlags.Instance | BindingFlags.Public;
    public static XElement WriteToElement(IXmlName obj)
    {
        var element = new XElement(obj.XmlName);
        WriteElementContent(obj, element);
        return element;
    }

    public static XElement WriteToElement(object obj)
    {
        var element = new XElement(obj.GetType().Name);
        WriteElementContent(obj, element);
        return element;
    }
        
    private static void WriteElementContent(object obj, XElement element) 
    {
        var thisType = obj.GetType();
        var attribType = typeof(XMLStorageAttribute);

        bool hasSetContent = false;
            
        foreach (var fieldInfo in thisType.GetFields(Flags))
        {
            var attribs = fieldInfo.GetCustomAttributes(attribType, false);
            if (attribs.Length < 1)
                continue;
            var attrib = (XMLStorageAttribute)attribs[0];
            if (fieldInfo.IsStatic)
            {
                Logger.Log(LogLevel.Error, $"Field cannot be static for XML storage: {fieldInfo.Name}");
                continue;
            }

            string val = XMLTypeConverter.ConvertToString(fieldInfo.GetValue(obj), attrib.Converter);
            if (attrib.IsContent)
            {
                if (hasSetContent)
                {
                    Logger.Log(LogLevel.Error, $"Already set the content of element {element.Name}");
                    continue;
                }
                    
                element.SetValue(val);
                hasSetContent = true;
            }
            else
            {
                element.SetAttributeValue(fieldInfo.Name, val);
            }
        }
        foreach (var propertyInfo in thisType.GetProperties(Flags))
        {
            var attribs = propertyInfo.GetCustomAttributes(attribType, false);
            if (attribs.Length < 1)
                continue;
            var attrib = (XMLStorageAttribute)attribs[0];
                
            var getMethod = propertyInfo.GetGetMethod();
            var setMethod = propertyInfo.GetSetMethod();
            if ((getMethod?.IsStatic ?? true) || (setMethod?.IsStatic ?? true))
            {
                Logger.Log(LogLevel.Error, $"Property cannot be static for XML storage: {propertyInfo.Name}");
                continue;
            }

            string val = XMLTypeConverter.ConvertToString(getMethod.Invoke(obj, null), attrib.Converter);
            if (attrib.IsContent)
            {
                if (hasSetContent)
                {
                    Logger.Log(LogLevel.Error, $"Already set the content of element {element.Name}");
                    continue;
                }
                    
                element.SetValue(val);
                hasSetContent = true;
            }
            else
            {
                element.SetAttributeValue(propertyInfo.Name, val);
            }
        }
    }

    public static void ReadFromElement(ElementInfo info, object obj)
    {
        var thisType = obj.GetType();
        var attribType = typeof(XMLStorageAttribute);

        bool hasSetContent = false;
            
        foreach (var fieldInfo in thisType.GetFields(Flags))
        {
            var attribs = fieldInfo.GetCustomAttributes(attribType, false);
            if (attribs.Length < 1)
                continue;
                
            var attrib = (XMLStorageAttribute)attribs[0];

            info.Attributes.TryGetValue(fieldInfo.Name, out var val);
            val = attrib.IsContent ? info.Content : val;

            if (val == null)
                continue;

            object trueVal = XMLTypeConverter.ConvertToType(fieldInfo.FieldType, val);
                
            if (attrib.IsContent)
            {
                if (hasSetContent)
                {
                    Logger.Log(LogLevel.Error, $"Already got the content of element {info.Name}");
                    continue;
                }
                    
                fieldInfo.SetValue(obj, trueVal);
                hasSetContent = true;
            }
            else
            {
                fieldInfo.SetValue(obj, trueVal);
            }
        }
        foreach (var propertyInfo in thisType.GetProperties(Flags))
        {
            var attribs = propertyInfo.GetCustomAttributes(attribType, false);
            if (attribs.Length < 1)
                continue;
            var attrib = (XMLStorageAttribute)attribs[0];
                
            var getMethod = propertyInfo.GetGetMethod();
            var setMethod = propertyInfo.GetSetMethod();
            if ((getMethod?.IsStatic ?? true) || (setMethod?.IsStatic ?? true))
            {
                Logger.Log(LogLevel.Error, $"Property cannot be static for XML storage: {propertyInfo.Name}");
                continue;
            }
                
            info.Attributes.TryGetValue(propertyInfo.Name, out var val);
            val = attrib.IsContent ? info.Content : val;

            if (val == null)
                continue;

            object trueVal = XMLTypeConverter.ConvertToType(propertyInfo.PropertyType, val);

            if (attrib.IsContent)
            {
                if (hasSetContent)
                {
                    Logger.Log(LogLevel.Error, $"Already got the content of element {info.Name}");
                    continue;
                }

                setMethod.Invoke(obj, new object[] { trueVal });
                hasSetContent = true;
            }
            else
            {
                setMethod.Invoke(obj, new object[] { trueVal });
            }
        }
    }
}

public interface IXmlName
{
    string XmlName { get; }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
