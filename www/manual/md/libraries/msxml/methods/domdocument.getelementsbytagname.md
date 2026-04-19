# DOMDocument.GetElementsByTagName Method

Returns all descendant elements in the document that match the given tag name.

## Syntax

```asp
Set oList = objXML.GetElementsByTagName(tagName)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `tagName` | String | Yes | The element tag name to search for. The match is case-insensitive. |

## Return Value

XMLNodeList. A list of all matching elements, ordered by document order. An empty XMLNodeList is returned if the document has no root or no elements match.

## Remarks

- The search traverses the entire document tree, not just direct children.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oList, i
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<books><book>A</book><book>B</book><book>C</book></books>"
Set oList = oXML.GetElementsByTagName("book")
For i = 0 To oList.Length - 1
    Response.Write oList.Item(i).Text & "<br>"
Next
Set oXML = Nothing
%>
```