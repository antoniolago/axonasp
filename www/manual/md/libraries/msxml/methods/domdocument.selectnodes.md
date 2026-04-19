# DOMDocument.SelectNodes Method

Evaluates an XPath expression against the document and returns all matching nodes.

## Syntax

```asp
Set oList = objXML.SelectNodes(xpath)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `xpath` | String | Yes | An XPath 1.0 expression to evaluate against the document. |

## Return Value

XMLNodeList. All nodes that satisfy the XPath expression in document order. Returns an empty XMLNodeList if no nodes match or the expression is empty.

## Remarks

- XPath is evaluated from the document root.
- The `//` axis, attribute predicates, positional predicates, `contains()`, `starts-with()`, `not()`, `and`, `or`, and namespace-qualified expressions are all supported.
- Use `SelectionNamespaces` on the document to bind namespace prefixes before querying.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oList, i
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<items><item cat='A'>One</item><item cat='B'>Two</item><item cat='A'>Three</item></items>"
Set oList = oXML.SelectNodes("//item[@cat='A']")
For i = 0 To oList.Length - 1
    Response.Write oList.Item(i).Text & "<br>"
Next
Set oXML = Nothing
%>
```