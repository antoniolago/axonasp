# XMLElement.LastChild Property

Returns the last direct child node of this element.

## Access

Read-only.

## Type

XMLElement or Null.

## Remarks

- Returns Null if the element has no children.

## Code Example

```asp
<%
Dim oXML, oRoot, oLast
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><a>First</a><b>Second</b></root>"
Set oRoot = oXML.DocumentElement
Set oLast = oRoot.LastChild
If Not IsNull(oLast) Then
    Response.Write oLast.Text
End If
Set oXML = Nothing
%>
```