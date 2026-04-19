# DOMDocument.CreateElement Method

Creates a new, unattached element node with the given tag name.

## Syntax

```asp
Set oElement = objXML.CreateElement(tagName)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `tagName` | String | Yes | The tag name for the new element. |

## Return Value

XMLElement. A new element node that is not yet attached to any document tree. Call `AppendChild` to attach it.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oRoot, oChild
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
Set oRoot = oXML.CreateElement("root")
Set oChild = oXML.CreateElement("item")
oChild.Text = "Hello"
oRoot.AppendChild oChild
oXML.AppendChild oRoot
Response.Write oXML.XML
Set oXML = Nothing
%>
```