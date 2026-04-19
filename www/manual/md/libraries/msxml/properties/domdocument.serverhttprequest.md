# DOMDocument.ServerHTTPRequest Property

Gets or sets whether HTTP requests issued by the document use the server HTTP stack.

## Access

Read/Write.

## Type

Boolean.

## Default

False.

## Remarks

- This property controls the HTTP client stack used when `Load` fetches content from an HTTP or HTTPS URL.
- Accepted for compatibility; the current implementation uses the same HTTP client regardless of this setting.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.ServerHTTPRequest = True
oXML.Load "https://example.com/data.xml"
Set oXML = Nothing
%>
```