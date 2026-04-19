# ServerXMLHTTP.Status Property

Returns the HTTP status code from the response.

## Access

Read-only.

## Type

Integer.

## Remarks

- Available after `Send` completes (`ReadyState = 4`).
- Common values: 200 (OK), 404 (Not Found), 500 (Internal Server Error).
- Returns 0 if no request has been sent or if the connection failed before any response was received.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/page", False
oHTTP.Send
Select Case oHTTP.Status
    Case 200
        Response.Write "OK: " & oHTTP.ResponseText
    Case 404
        Response.Write "Not found."
    Case Else
        Response.Write "HTTP " & oHTTP.Status & ": " & oHTTP.StatusText
End Select
Set oHTTP = Nothing
%>
```