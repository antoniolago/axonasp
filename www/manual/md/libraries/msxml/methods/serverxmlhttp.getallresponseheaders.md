# ServerXMLHTTP.GetAllResponseHeaders Method

Returns all response headers as a single CRLF-delimited string.

## Syntax

```asp
headers = objHTTP.GetAllResponseHeaders()
```

## Parameters

None.

## Return Value

String. All response headers concatenated in `Header: Value\r\n` format. Returns an empty String if no response has been received.

## Remarks

- Call this method only after `Send` has completed (`ReadyState = 4`).
- Each line is of the form `Header-Name: value` followed by a carriage return and line feed (`\r\n`).
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oHTTP, sHeaders
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/", False
oHTTP.Send
sHeaders = oHTTP.GetAllResponseHeaders()
Response.Write "<pre>" & Server.HTMLEncode(sHeaders) & "</pre>"
Set oHTTP = Nothing
%>
```