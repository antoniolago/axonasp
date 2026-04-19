# DOMDocument.SelectSingleNode Method

Evaluates an XPath expression against the document and returns the first matching node.

## Syntax

```asp
Set oNode = objXML.SelectSingleNode(xpath)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `xpath` | String | Yes | An XPath 1.0 expression to evaluate against the document. |

## Return Value

XMLElement. The first node that satisfies the XPath expression. Returns Null if no node matches or the expression is empty.

## Remarks

- XPath is evaluated from the document root.
- The `//` axis, attribute predicates (`@attr`), positional predicates, `contains()`, `starts-with()`, `not()`, and namespace-qualified expressions (when `SelectionNamespaces` is set) are all supported.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<users><user id='1'>Alice</user><user id='2'>Bob</user></users>"
Set oNode = oXML.SelectSingleNode("//user[@id='2']")
If Not IsNull(oNode) Then
    Response.Write oNode.Text
End If
Set oXML = Nothing
%>
```