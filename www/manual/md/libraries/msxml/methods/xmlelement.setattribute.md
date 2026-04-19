# XMLElement.SetAttribute Method

Creates or replaces an attribute on this element.

## Syntax

```asp
oElement.SetAttribute name, value
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | The attribute name. |
| `value` | String | Yes | The value to assign to the attribute. |

## Return Value

Empty. This method does not return a value.

## Remarks

- If an attribute with the same name already exists, its value is replaced.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oElem
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
Set oElem = oXML.CreateElement("product")
oElem.SetAttribute "id", "101"
oElem.SetAttribute "category", "electronics"
oElem.Text = "Gadget"
oXML.AppendChild oElem
Response.Write oXML.XML
Set oXML = Nothing
%>
```