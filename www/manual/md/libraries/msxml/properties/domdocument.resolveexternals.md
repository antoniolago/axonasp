# DOMDocument.ResolveExternals Property

Gets or sets whether external entities and document type definitions are resolved during parsing.

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
oXML.ResolveExternals = False
oXML.LoadXML "<root/>"
Set oXML = Nothing
%>
```