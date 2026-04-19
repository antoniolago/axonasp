# ServerXMLHTTP.SetRequestHeader Method

Adds or replaces a request header that will be sent with the next `Send` call.

## Syntax

```asp
objHTTP.SetRequestHeader header, value
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `header` | String | Yes | The name of the HTTP header (e.g., `"Content-Type"`, `"Accept"`). |
| `value` | String | Yes | The value to assign to the header. |

## Return Value

Empty. This method does not return a value.

## Remarks

- If a header with the same name is already set, its value is replaced.
- Headers are stored until `Open` is called on a new request or the object is released.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/data.xml", False
oHTTP.SetRequestHeader "Accept", "application/xml"
oHTTP.SetRequestHeader "Authorization", "Bearer mytoken"
oHTTP.Send
Response.Write oHTTP.ResponseText
Set oHTTP = Nothing
%>
```