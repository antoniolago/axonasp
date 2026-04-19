# XMLElement.AppendChild Method

Appends a child node to this element and returns the appended node.

## Syntax

```asp
Set oResult = oElement.AppendChild(child)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `child` | XMLElement | Yes | The node to append as a direct child of this element. |

## Return Value

XMLElement. Returns the appended `child` node.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oParent, oChild
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root></root>"
Set oParent = oXML.DocumentElement
Set oChild = oXML.CreateElement("entry")
oChild.Text = "New entry"
oParent.AppendChild oChild
Response.Write oXML.XML
Set oXML = Nothing
%>
```