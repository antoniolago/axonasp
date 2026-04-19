# DOMDocument.XML Property

Returns the XML source string or the serialized representation of the current document tree.

## Access

Read-only.

## Type

String.

## Remarks

- If the document was loaded with `LoadXML`, the original XML string is returned.
- If the document was built programmatically using `CreateElement` and `AppendChild`, the tree is serialized to an XML string.
- Returns an empty String if no document has been loaded.

## Code Example

```asp
<%
Dim oXML, oRoot, oItem
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
Set oRoot = oXML.CreateElement("list")
Set oItem = oXML.CreateElement("entry")
oItem.Text = "Hello"
oRoot.AppendChild oItem
oXML.AppendChild oRoot
Response.Write oXML.XML
Set oXML = Nothing
%>
```