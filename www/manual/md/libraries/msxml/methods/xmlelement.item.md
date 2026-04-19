# XMLElement.Item Method

Returns the direct child node at a given zero-based index.

## Syntax

```asp
Set oChild = oElement.Item(index)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `index` | Integer | Yes | Zero-based position among the direct children of this element. |

## Return Value

XMLElement. The child node at the specified index. Returns Null if the index is out of range.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oRoot, oChild
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><a>1</a><b>2</b></root>"
Set oRoot = oXML.DocumentElement
Set oChild = oRoot.Item(0)
Response.Write oChild.NodeName & ": " & oChild.Text
Set oXML = Nothing
%>
```