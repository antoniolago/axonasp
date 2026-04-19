# XMLElement.Children Property

Returns a list of all direct child nodes of this element. This is an alias for `ChildNodes`.

## Access

Read-only.

## Type

XMLNodeList.

## Remarks

- Identical in behaviour to `ChildNodes`. Either property can be used interchangeably.
- Returns an empty XMLNodeList if the element has no children.

## Code Example

```asp
<%
Dim oXML, oRoot, oList
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><x/><y/></root>"
Set oRoot = oXML.DocumentElement
Set oList = oRoot.Children
Response.Write "Child count: " & oList.Length
Set oXML = Nothing
%>
```