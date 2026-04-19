# ParseError.FilePos Property

Returns the byte offset in the source document where the parse error was detected.

## Access

Read-only.

## Type

Integer.

## Remarks

- Returns 0 when there is no error or when the position cannot be determined.
- Use `Line` and `LinePos` for line-and-column positioning.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<a><b></a>") Then
    Response.Write "Error at byte offset: " & oXML.ParseError.FilePos
End If
Set oXML = Nothing
%>
```