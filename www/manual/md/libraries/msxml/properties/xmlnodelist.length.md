# XMLNodeList.Length Property

Returns the number of nodes in the list.

## Access

Read-only.

## Type

Integer.

## Remarks

- Use this property to iterate the list with `Item(0)` through `Item(Length - 1)`.
- Returns 0 for an empty list.

## Code Example

```asp
<%
Dim oXML, oList, i
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<r><a/><b/><c/></r>"
Set oList = oXML.DocumentElement.ChildNodes
For i = 0 To oList.Length - 1
    Response.Write oList.Item(i).NodeName & "<br>"
Next
Set oXML = Nothing
%>
```