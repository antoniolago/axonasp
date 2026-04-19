# ParseError.Reason Property

Returns a human-readable description of the parse error.

## Access

Read-only.

## Type

String.

## Remarks

- Returns an empty String when `ErrorCode` is 0 (no error).
- For HTTP load failures, the reason string describes the network or server error.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<open") Then
    Response.Write "Reason: " & oXML.ParseError.Reason
End If
Set oXML = Nothing
%>
```