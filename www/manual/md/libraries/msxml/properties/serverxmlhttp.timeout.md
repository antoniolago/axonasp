# ServerXMLHTTP.Timeout Property

Gets or sets the maximum number of seconds to wait for a response before the request fails.

## Access

Read/Write.

## Type

Integer.

## Default

30 seconds.

## Remarks

- Set this property before calling `Send`.
- If the server does not respond within the configured time, `Send` returns with an error condition and `Status` is set to 0.
- Setting `Timeout` to 0 is not recommended as it may cause indefinite blocking.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Timeout = 10
oHTTP.Open "GET", "https://example.com/slow-endpoint", False
On Error Resume Next
oHTTP.Send
If Err.Number <> 0 Then
    Response.Write "Request timed out."
    Err.Clear
Else
    Response.Write oHTTP.ResponseText
End If
Set oHTTP = Nothing
%>
```