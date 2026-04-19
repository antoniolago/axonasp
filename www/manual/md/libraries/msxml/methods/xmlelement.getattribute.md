# XMLElement.GetAttribute Method

Returns the value of the named attribute on this element.

## Syntax

```asp
value = oElement.GetAttribute(name)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | The attribute name to look up. |

## Return Value

String. The value of the named attribute. Returns an empty String if the attribute does not exist.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<item id='99' name='Widget'/>"
Set oNode = oXML.DocumentElement
Response.Write "id=" & oNode.GetAttribute("id") & ", name=" & oNode.GetAttribute("name")
Set oXML = Nothing
%>
```