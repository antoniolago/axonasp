# XMLElement.SelectSingleNode Method

Evaluates an XPath expression relative to this element and returns the first matching node.

## Syntax

```asp
Set oNode = oElement.SelectSingleNode(xpath)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `xpath` | String | Yes | An XPath 1.0 expression evaluated relative to this element. |

## Return Value

XMLElement. The first matching node. Returns Null if no node matches or the expression is empty.

## Remarks

- When the XPath expression starts with `/`, it is evaluated from the document root rather than the current element.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oSection, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><section><item id='3'>Target</item></section></root>"
Set oSection = oXML.SelectSingleNode("//section")
Set oNode = oSection.SelectSingleNode("item[@id='3']")
If Not IsNull(oNode) Then
    Response.Write oNode.Text
End If
Set oXML = Nothing
%>
```