# XMLElement.GetElementsByTagName Method

Returns all descendant elements of this element that match the given tag name.

## Syntax

```asp
Set oList = oElement.GetElementsByTagName(tagName)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `tagName` | String | Yes | The tag name to search for. The match is case-insensitive. |

## Return Value

XMLNodeList. All matching descendant elements in document order. Returns an empty XMLNodeList if no elements match.

## Remarks

- The search includes all levels of descendants, not just direct children.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oRoot, oList, i
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><section><item>A</item></section><item>B</item></root>"
Set oRoot = oXML.DocumentElement
Set oList = oRoot.GetElementsByTagName("item")
For i = 0 To oList.Length - 1
    Response.Write oList.Item(i).Text & "<br>"
Next
Set oXML = Nothing
%>
```