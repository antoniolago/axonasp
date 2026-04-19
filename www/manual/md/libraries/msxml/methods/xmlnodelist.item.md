# XMLNodeList.Item Method

Returns the node at a given zero-based index from the list.

## Syntax

```asp
Set oNode = oList.Item(index)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `index` | Integer | Yes | Zero-based position of the node to retrieve. |

## Return Value

XMLElement. The node at the specified index. Returns Null if the index is negative or greater than or equal to `Length`.

## Remarks

- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oList, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<list><a>1</a><b>2</b><c>3</c></list>"
Set oList = oXML.DocumentElement.ChildNodes
Set oNode = oList.Item(1)
Response.Write oNode.NodeName & ": " & oNode.Text
Set oXML = Nothing
%>
```