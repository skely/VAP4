# XML Basics

- **XML:** Extensible Markup Language (rozšiřitelný značkovací jazyk)
- **developed by:** World Wide Web Consortium (W3C)
- **use:** for *data serialization*, where it competes with *JSON* and *YAML*. XML processing is supported by a variety of tools and programming languages.
- **data serialization:** converting a data structure or object instance stored in the computer's internal memory into a sequence of bits that can be stored on some medium or transferred over a network.

## Key Concepts in XML
- **Tags:** XML uses tags to define ```elements```. Each element is enclosed in opening and closing tags, like ```<tagname>``` and ```</tagname>.```
- **Elements:** Elements are the building blocks of an XML document, often referred to as nodes. They consist of a ```start tag```, content, and an ```end tag```.
- **Root Element:** Every XML document must have a single root element that encloses all other elements.
- **Hierarchy:** XML documents have a tree-like structure where elements can be nested inside other elements, creating a parent-child relationship.
- **Attributes:** Elements can have attributes, which provide additional information about an element. Attributes are placed inside the opening tag.

## XML Syntax
- **Prolog:** The prolog is optional but recommended. It contains information about the XML version and character encoding:
```xml
<?xml version="1.0" encoding="UTF-8"?>
```
- **Elements:** Elements are represented with tags:
```xml
<book>
    <title>XML for Beginners</title>
    <author>John Doe</author>
</book>
```
- **Attributes:** Elements can have attributes to add extra information:
```xml
<book genre="fiction">
    <title>XML for Beginners</title>
</book>
```

## Example of an XML Document
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!-- this is a comment and it does nothing -->
<selfClosingTag/> <!-- this is example of self-closing tag -->
<image src="photo.png"/> 
<bookstore>
   <book category="fiction">
      <title lang="en">Harry Potter</title>
      <author>J.K. Rowling</author>
      <year>2005</year>
      <price>29.99</price>
   </book>
   <book category="non-fiction">
      <title lang="en">Sapiens</title>
      <author>Yuval Noah Harari</author>
      <year>2011</year>
      <price>19.99</price>
   </book>
</bookstore>
```

## Key Points to Remember
- **Case Sensitivity:** XML tags are case-sensitive (<Title> and <title> are different).
- **Well-Formed:** XML documents must be well-formed, meaning all tags must be properly nested and closed.
- **Self-Closing Tags:** If an element has no content, it can be self-closed: ``` <bookstore/> ```
- **Comments:** You can include comments using: ```<!-- comment -->```

## Why Use XML?
- Data Transport: XML is often used to transport data between systems or applications.
- Data Storage: XML files can be used to store data in a structured way, independent of how it will be displayed.
- Platform Independent: XML can be read and processed on any platform, making it highly portable.

## Tools to Work with XML
- Browsers: Most modern web browsers can display XML files directly.
- XML Editors: Tools like Notepad++, VS Code, or XMLSpy provide syntax highlighting and validation for XML documents.

## Final Tips:
- XML focuses on what data is, not how it looks.
- Always ensure that XML files are "well-formed" by properly closing all tags.
- XML is extensible, meaning you can define your own tags to suit your specific needs.
  
