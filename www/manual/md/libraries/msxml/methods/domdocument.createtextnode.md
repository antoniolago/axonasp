# DOMDocument.CreateTextNode Method

Creates a new text node with the given string value.

## Syntax

```asp
Set oTextNode = objXML.CreateTextNode(text)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `text` | String | Yes | The text content of the new node. |

## Return Value

XMLElement. A new text node (NodeName = `#text`) that is not yet attached to any parent. Call `AppendChild` on the target element to attach it.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oElem, oText
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
Set oElem = oXML.CreateElement("title")
Set oText = oXML.CreateTextNode("My Title")
oElem.AppendChild oText
oXML.AppendChild oElem
Response.Write oXML.XML
Set oXML = Nothing
%>
```