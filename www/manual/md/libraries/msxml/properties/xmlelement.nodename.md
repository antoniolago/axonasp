# XMLElement.NodeName Property

Returns the tag name of the element node.

## Access

Read-only.

## Type

String.

## Remarks

- For element nodes, this is the XML tag name (e.g., `"product"`, `"item"`).
- For text nodes created with `CreateTextNode`, the value is `"#text"`.
- For attribute nodes created with `CreateAttribute`, the value is the attribute name.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<catalog><item>Widget</item></catalog>"
Set oNode = oXML.SelectSingleNode("//item")
Response.Write oNode.NodeName
Set oXML = Nothing
%>
```