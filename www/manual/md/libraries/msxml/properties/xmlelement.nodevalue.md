# XMLElement.NodeValue Property

Gets or sets the value of the node.

## Access

Read/Write.

## Type

String.

## Remarks

- For text nodes (`NodeName = "#text"`), this property holds the text content.
- For attribute nodes, this holds the attribute value.
- For element nodes, this property is typically empty; use the `Text` property to get concatenated text content.
- Setting `NodeValue` replaces the node's current value.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<msg>Hello</msg>"
Set oNode = oXML.DocumentElement.FirstChild
Response.Write "NodeValue: " & oNode.NodeValue
Set oXML = Nothing
%>
```