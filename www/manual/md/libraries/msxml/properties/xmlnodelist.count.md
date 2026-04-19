# XMLNodeList.Count Property

Returns the number of nodes in the list. This is an alias for `Length`.

## Access

Read-only.

## Type

Integer.

## Remarks

- Identical in behaviour to `Length`. Either property can be used interchangeably.
- Returns 0 for an empty list.

## Code Example

```asp
<%
Dim oXML, oList
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<r><a/><b/></r>"
Set oList = oXML.DocumentElement.ChildNodes
Response.Write "Count: " & oList.Count
Set oXML = Nothing
%>
```