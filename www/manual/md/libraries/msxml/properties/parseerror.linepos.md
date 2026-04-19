# ParseError.LinePos Property

Returns the 1-based column position within the error line where the parse error was detected.

## Access

Read-only.

## Type

Integer.

## Remarks

- Returns 0 when there is no error.
- Pair with `Line` for a precise error location.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<root><bad") Then
    Response.Write "Line " & oXML.ParseError.Line & ", Col " & oXML.ParseError.LinePos
End If
Set oXML = Nothing
%>
```