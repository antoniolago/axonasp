# ParseError.SrcText Property

Returns the source text that was being parsed when the error occurred.

## Access

Read-only.

## Type

String.

## Remarks

- Contains the text fragment around the error position.
- Returns an empty String when there is no error.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<root><item broken") Then
    Response.Write "Near: " & oXML.ParseError.SrcText
End If
Set oXML = Nothing
%>
```