# XMLElement.SelectNodes Method

Evaluates an XPath expression relative to this element and returns all matching nodes.

## Syntax

```asp
Set oList = oElement.SelectNodes(xpath)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `xpath` | String | Yes | An XPath 1.0 expression evaluated relative to this element. |

## Return Value

XMLNodeList. All matching nodes in document order. Returns an empty XMLNodeList if no nodes match or the expression is empty.

## Remarks

- When the XPath expression starts with `/`, it is evaluated from the document root.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oSection, oList, i
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><group><item>A</item><item>B</item></group></root>"
Set oSection = oXML.SelectSingleNode("//group")
Set oList = oSection.SelectNodes("item")
For i = 0 To oList.Length - 1
    Response.Write oList.Item(i).Text & "<br>"
Next
Set oXML = Nothing
%>
```