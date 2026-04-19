# ServerXMLHTTP.StatusText Property

Returns the full HTTP status line from the response.

## Access

Read-only.

## Type

String.

## Remarks

- Available after `Send` completes (`ReadyState = 4`).
- The value includes the status code and reason phrase, for example `200 OK` or `404 Not Found`.
- Returns an empty String if no response has been received.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/", False
oHTTP.Send
Response.Write "Status: " & oHTTP.StatusText
Set oHTTP = Nothing
%>
```