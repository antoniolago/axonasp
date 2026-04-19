# XMLElement.Attributes Property

Returns a collection of the element's attribute name/value pairs.

## Access

Read-only.

## Type

Collection (array of name/value maps).

## Remarks

- Each entry in the collection represents one attribute.
- Use `GetAttribute` and `SetAttribute` for direct attribute read/write by name.
- The order of attributes in the collection is not guaranteed.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<item id='5' name='Widget'/>"
Set oNode = oXML.DocumentElement
Response.Write "id=" & oNode.GetAttribute("id") & ", name=" & oNode.GetAttribute("name")
Set oXML = Nothing
%>
```