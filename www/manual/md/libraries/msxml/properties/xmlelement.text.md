# XMLElement.Text Property

Gets or sets the concatenated text content of the element and all its descendants.

## Access

Read/Write.

## Type

String.

## Remarks

- When read, the property traverses the full subtree and concatenates all text node values.
- When assigned, the element's child nodes are replaced with a single new text node containing the given string.
- For a node with no text content, returns an empty String.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><a>Hello </a><b>World</b></root>"
Set oNode = oXML.DocumentElement
Response.Write oNode.Text
Set oXML = Nothing
%>
```