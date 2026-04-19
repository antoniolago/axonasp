# XMLElement.Length Property

Returns the number of direct child nodes of this element.

## Access

Read-only.

## Type

Integer.

## Remarks

- Equivalent to `ChildNodes.Length`.
- Returns 0 if the element has no children.

## Code Example

```asp
<%
Dim oXML, oRoot
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><a/><b/><c/></root>"
Set oRoot = oXML.DocumentElement
Response.Write "Children: " & oRoot.Length
Set oXML = Nothing
%>
```