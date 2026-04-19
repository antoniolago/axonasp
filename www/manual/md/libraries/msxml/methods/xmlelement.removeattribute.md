# XMLElement.RemoveAttribute Method

Removes the named attribute from this element.

## Syntax

```asp
oElement.RemoveAttribute name
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | The name of the attribute to remove. |

## Return Value

Empty. This method does not return a value.

## Remarks

- If the attribute does not exist, the call is silently ignored.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<item id='1' temp='yes'/>"
Set oNode = oXML.DocumentElement
oNode.RemoveAttribute "temp"
Response.Write oXML.XML
Set oXML = Nothing
%>
```