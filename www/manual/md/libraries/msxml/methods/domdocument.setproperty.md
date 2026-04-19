# DOMDocument.SetProperty Method

Sets a named document property that controls parsing and query behaviour.

## Syntax

```asp
objXML.SetProperty name, value
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | The name of the property to set. |
| `value` | Variant | Yes | The new value for the property. |

## Return Value

Empty. This method does not return a value.

## Remarks

- This method is equivalent to assigning the corresponding named property directly.
- The most commonly used property is `SelectionNamespaces`, which binds namespace prefixes for XPath queries. Format: `xmlns:prefix='uri'`.
- Setting an unknown property name is silently ignored.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<ns:root xmlns:ns='urn:test'><ns:item>Value</ns:item></ns:root>"
oXML.SetProperty "SelectionNamespaces", "xmlns:ns='urn:test'"
Set oNode = oXML.SelectSingleNode("//ns:item")
If Not IsNull(oNode) Then
    Response.Write oNode.Text
End If
Set oXML = Nothing
%>
```