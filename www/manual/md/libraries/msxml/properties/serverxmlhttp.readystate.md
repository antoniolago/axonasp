# ServerXMLHTTP.ReadyState Property

Returns the current lifecycle state of the HTTP request.

## Access

Read-only.

## Type

Integer.

## Values

| Value | Name | Description |
|---|---|---|
| 0 | Uninitialized | The object has been created but `Open` has not been called. |
| 1 | Open | `Open` has been called but `Send` has not been called. |
| 2 | Sent | `Send` has been called but no response has been received yet. |
| 3 | Receiving | Response headers have been received; body is being received. |
| 4 | Complete | The response is fully received and available. |

## Remarks

- Because the implementation is synchronous, `ReadyState` transitions directly from 1 to 4 when `Send` returns.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
Response.Write "Before Open: " & oHTTP.ReadyState & "<br>"
oHTTP.Open "GET", "https://example.com/", False
Response.Write "After Open: " & oHTTP.ReadyState & "<br>"
oHTTP.Send
Response.Write "After Send: " & oHTTP.ReadyState & "<br>"
Set oHTTP = Nothing
%>
```