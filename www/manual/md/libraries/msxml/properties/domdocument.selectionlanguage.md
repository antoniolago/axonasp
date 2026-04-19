# DOMDocument.SelectionLanguage Property

Gets or sets the query language used by `SelectSingleNode` and `SelectNodes`.

## Access

Read/Write.

## Type

String.

## Default

`"XPath"`

## Remarks

- The only currently supported value is `XPath`.
- Setting this property is equivalent to calling `SetProperty "SelectionLanguage", value`.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.SelectionLanguage = "XPath"
oXML.LoadXML "<root><item>A</item></root>"
Response.Write oXML.SelectSingleNode("//item").Text
Set oXML = Nothing
%>
```