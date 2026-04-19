# DOMDocument.DocumentElement Property

Returns the root element of the parsed document.

## Access

Read-only.

## Type

XMLElement or Null.

## Remarks

- Returns Null if the document has not been loaded, or if `LoadXML` or `Load` failed.
- The returned XMLElement is the top-level element of the document tree.

## Code Example

```asp
<%
Dim oXML, oRoot
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<catalog><item>First</item></catalog>"
Set oRoot = oXML.DocumentElement
If Not IsNull(oRoot) Then
    Response.Write "Root element: " & oRoot.NodeName
End If
Set oXML = Nothing
%>
```