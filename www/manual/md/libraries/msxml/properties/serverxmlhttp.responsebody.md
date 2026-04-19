# ServerXMLHTTP.ResponseBody Property

Returns the raw response body as a byte array.

## Access

Read-only.

## Type

Byte Array.

## Remarks

- Available after `Send` completes (`ReadyState = 4`).
- The returned array contains the unprocessed response bytes with no character decoding applied.
- Useful for downloading binary content such as images, PDFs, or compressed files.
- Returns an empty array if no response has been received.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/file.zip", False
oHTTP.Send
If oHTTP.Status = 200 Then
    Response.BinaryWrite oHTTP.ResponseBody
End If
Set oHTTP = Nothing
%>
```