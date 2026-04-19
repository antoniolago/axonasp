# XMLElement.XML Property

Returns the serialized XML markup of this node and its entire subtree.

## Access

Read-only.

## Type

String.

## Remarks

- The returned string includes the element's opening tag, all child nodes serialized recursively, and the closing tag.
- Attributes on the element are included in the opening tag.
- Use `DOMDocument.XML` to serialize the complete document.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><child id='1'>Content</child></root>"
Set oNode = oXML.SelectSingleNode("//child")
Response.Write oNode.XML
Set oXML = Nothing
%>
```