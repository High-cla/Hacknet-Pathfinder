---
title: PathfinderAPI/Util/XML/EventReader.cs

---

# PathfinderAPI/Util/XML/EventReader.cs



## Namespaces

| Name           |
| -------------- |
| **[Pathfinder](../Namespaces/namespace_pathfinder/)**  |
| **[Pathfinder::Util](../Namespaces/namespace_pathfinder_1_1_util/)**  |
| **[Pathfinder::Util::XML](../Namespaces/namespace_pathfinder_1_1_util_1_1_x_m_l/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[Pathfinder::Util::XML::EventReader](../Classes/class_pathfinder_1_1_util_1_1_x_m_l_1_1_event_reader/)**  |




## Source code

```csharp
using System.Xml;

namespace Pathfinder.Util.XML;

public class EventReader
{
    protected virtual bool Read() => true;
    protected virtual bool ReadDocument() => true;
    protected virtual void ReadElement(Dictionary<string, string> attributes) {}
    protected virtual void ReadEndElement() {}
    protected virtual void ReadText() {}
    protected virtual void EndRead() {}
        
    public XmlReader Reader { get; protected set; }
    public List<string> ParentNames = new List<string>();
    public string CurrentNamespace => string.Join(".", ParentNames);
        
    protected string Text;
        
    public EventReader() {}
        
    public EventReader(string text, bool isPath)
    {
        Text = isPath ? File.ReadAllText(text) : text;
    }

    public EventReader(XmlReader rdr)
    {
        Reader = rdr;
    }

    public void SetText(string text, bool isPath)
    {
        Text = isPath ? File.ReadAllText(text) : text;
    }

    public void Parse()
    {
        ParentNames.Clear();
            
        // verify xml is formatted legally
        if (Reader == null)
            using (XmlReader reader = XmlReader.Create(new StringReader(Text))) while (reader.Read());

        using (Reader ??= XmlReader.Create(new StringReader(Text)))
        {
            while (Reader.Read())
            {
                if (Read())
                {
                    switch (Reader.NodeType)
                    {
                        case XmlNodeType.Document:
                            if (!ReadDocument()) return;
                            break;
                        case XmlNodeType.Element:
                            var attributes = new Dictionary<string, string>();

                            if (Reader.HasAttributes)
                            {
                                while (Reader.MoveToNextAttribute())
                                {
                                    attributes.Add(Reader.Name, Reader.Value);
                                }

                                Reader.MoveToElement();
                            }
                                
                            ParentNames.Add(Reader.Name);
                            ReadElement(attributes);

                            if (Reader.IsEmptyElement)
                            {
                                ReadEndElement();
                                ParentNames.RemoveAt(ParentNames.Count - 1);
                            }
                                
                            break;
                        case XmlNodeType.EndElement:
                            ReadEndElement();
                            ParentNames.RemoveAt(ParentNames.Count - 1);
                            break;
                        case XmlNodeType.SignificantWhitespace:
                        case XmlNodeType.CDATA:
                        case XmlNodeType.Text:
                            ReadText();
                            break;
                    }
                }
            }
                
            EndRead();
        }

        Reader = null;
    }

    public bool TryParse(out Exception exception)
    {
        try
        {
            Parse();
            exception = null;
            return true;
        }
        catch (Exception e)
        {
            exception = e;
            return false;
        }
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:20:08 +0000
