# ParseError.ErrorCode Property

Returns the numeric error code from the last parse operation.

## Access

Read-only.

## Type

Integer.

## Remarks

- A value of 0 indicates the document was parsed successfully.
- A negative value (typically -1) indicates a general parse or file-load failure.
- When `DOMDocument.Load` fails due to an HTTP error, this property is set to the HTTP status code (e.g., 404, 500).
- Always check this property after `LoadXML` or `Load` returns False before accessing document content.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<bad<xml") Then
    Response.Write "Parse failed. ErrorCode: " & oXML.ParseError.ErrorCode
End If
Set oXML = Nothing
%>
```