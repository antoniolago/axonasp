# ParseError.Line Property

Returns the 1-based line number in the source document where the parse error was detected.

## Access

Read-only.

## Type

Integer.

## Remarks

- Returns 0 when there is no error.
- Pair with `LinePos` to identify the exact error location.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<root>" & Chr(10) & "<bad attr") Then
    Response.Write "Error on line: " & oXML.ParseError.Line
End If
Set oXML = Nothing
%>
```