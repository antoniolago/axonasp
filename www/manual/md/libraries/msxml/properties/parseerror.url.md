# ParseError.URL Property

Returns the URL or file path that was being loaded when the error occurred.

## Access

Read-only.

## Type

String.

## Remarks

- Populated when `Load` fails, and contains the URL or resolved file path that was requested.
- Returns an empty String when the document was loaded via `LoadXML` or when there is no error.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.Load("https://example.com/missing.xml") Then
    Response.Write "Failed to load: " & oXML.ParseError.URL
    Response.Write " (" & oXML.ParseError.Reason & ")"
End If
Set oXML = Nothing
%>
```