# DOMDocument.CreateAttribute Method

Creates a new, unattached attribute node with the given name.

## Syntax

```asp
Set oAttr = objXML.CreateAttribute(name)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | The name of the attribute. |

## Return Value

XMLElement. A new attribute node not yet attached to any element. Set its `NodeValue` property to assign the attribute value, then use `SetAttribute` on the target element.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oElem
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
Set oElem = oXML.CreateElement("item")
oElem.SetAttribute "id", "42"
oXML.AppendChild oElem
Response.Write oXML.XML
Set oXML = Nothing
%>
```