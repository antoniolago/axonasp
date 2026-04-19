# DOMDocument.SelectionNamespaces Property

Gets or sets the namespace prefix bindings used during XPath queries.

## Access

Read/Write.

## Type

String.

## Remarks

- The value is a space-separated list of namespace declarations in the format `xmlns:prefix='uri'`.
- Setting this property is equivalent to calling `SetProperty "SelectionNamespaces", value`.
- Must be set before calling `SelectSingleNode` or `SelectNodes` on namespace-qualified documents.

## Code Example

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<ns:catalog xmlns:ns='urn:example'><ns:item>Widget</ns:item></ns:catalog>"
oXML.SelectionNamespaces = "xmlns:ns='urn:example'"
Set oNode = oXML.SelectSingleNode("//ns:item")
If Not IsNull(oNode) Then
    Response.Write oNode.Text
End If
Set oXML = Nothing
%>
```