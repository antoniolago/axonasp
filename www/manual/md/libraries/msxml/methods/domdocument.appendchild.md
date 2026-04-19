# DOMDocument.AppendChild Method

Attaches a child element to the document root. If the document has no root yet, the element becomes the root; otherwise it is appended as a child of the existing root.

## Syntax

```asp
Set oResult = objXML.AppendChild(child)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `child` | XMLElement | Yes | The element node to attach to the document. |

## Return Value

XMLElement. Returns the appended `child` node.

## Remarks

- To build a complete document tree, call `CreateElement` on each node, build the sub-tree with `XMLElement.AppendChild`, then call `DOMDocument.AppendChild` with the root element.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oRoot, oItem
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
Set oRoot = oXML.CreateElement("products")
Set oItem = oXML.CreateElement("product")
oItem.Text = "Widget"
oRoot.AppendChild oItem
oXML.AppendChild oRoot
Response.Write oXML.XML
Set oXML = Nothing
%>
```