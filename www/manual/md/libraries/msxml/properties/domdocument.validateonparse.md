# DOMDocument.ValidateOnParse Property

Gets or sets whether the document is validated against its DTD or schema during parsing.

## Access

Read/Write.

## Type

Boolean.

## Default

False.

## Remarks

- Accepted for compatibility with existing code. Set this property before calling `Load` or `LoadXML`.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.ValidateOnParse = False
oXML.LoadXML "<root/>"
Set oXML = Nothing
%>
```