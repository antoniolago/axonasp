# DOMDocument.GetProperty Method

Returns the current value of a named document property.

## Syntax

```asp
value = objXML.GetProperty(name)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | The name of the property to retrieve (e.g., `"SelectionLanguage"`, `"SelectionNamespaces"`). |

## Return Value

Variant. The current value of the named property. Returns Empty if the property name is not recognized.

## Remarks

- This method is equivalent to reading the corresponding named property directly (e.g., `objXML.SelectionNamespaces`).
- Recognised property names: `SelectionLanguage`, `SelectionNamespaces`, `ResolveExternals`, `ValidateOnParse`, `PreserveWhiteSpace`, `ServerHTTPRequest`, `Async`.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, sLang
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
sLang = oXML.GetProperty("SelectionLanguage")
Response.Write "SelectionLanguage: " & sLang
Set oXML = Nothing
%>
```