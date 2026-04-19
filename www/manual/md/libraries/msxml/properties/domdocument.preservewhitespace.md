# DOMDocument.PreserveWhiteSpace Property

Gets or sets whether insignificant whitespace text nodes are preserved in the document tree.

## Access

Read/Write.

## Type

Boolean.

## Default

False.

## Remarks

- When False, whitespace-only text nodes between elements are discarded during parsing.
- Set this property before calling `Load` or `LoadXML`.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.PreserveWhiteSpace = False
oXML.LoadXML "<root>  <item>A</item>  </root>"
Response.Write oXML.DocumentElement.ChildNodes.Length
Set oXML = Nothing
%>
```