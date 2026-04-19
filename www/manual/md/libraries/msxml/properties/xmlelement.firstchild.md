# XMLElement.FirstChild Property

Returns the first direct child node of this element.

## Access

Read-only.

## Type

XMLElement or Null.

## Remarks

- Returns Null if the element has no children.

## Code Example

```asp
<%
Dim oXML, oRoot, oFirst
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><a>First</a><b>Second</b></root>"
Set oRoot = oXML.DocumentElement
Set oFirst = oRoot.FirstChild
If Not IsNull(oFirst) Then
    Response.Write oFirst.Text
End If
Set oXML = Nothing
%>
```