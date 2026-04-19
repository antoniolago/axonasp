# ServerXMLHTTP.ResponseText Property

Returns the response body decoded as a text string.

## Access

Read-only.

## Type

String.

## Remarks

- Available after `Send` completes (`ReadyState = 4`).
- The response body is decoded using the charset specified by the server's `Content-Type` response header. Falls back to UTF-8 if no charset is present.
- Returns an empty String if no request has been sent or the body is empty.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/data.txt", False
oHTTP.Send
If oHTTP.Status = 200 Then
    Response.Write oHTTP.ResponseText
End If
Set oHTTP = Nothing
%>
```