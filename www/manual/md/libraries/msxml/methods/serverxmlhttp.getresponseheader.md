# ServerXMLHTTP.GetResponseHeader Method

Returns the value of a single response header by name.

## Syntax

```asp
value = objHTTP.GetResponseHeader(header)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `header` | String | Yes | The name of the response header to retrieve. The lookup is case-insensitive. |

## Return Value

String. The value of the specified header. Returns an empty String if the header is not present in the response.

## Remarks

- Call this method only after `Send` has completed (`ReadyState = 4`).
- The header name lookup is case-insensitive.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oHTTP, sContentType
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/data", False
oHTTP.Send
sContentType = oHTTP.GetResponseHeader("Content-Type")
Response.Write "Content-Type: " & sContentType
Set oHTTP = Nothing
%>
```