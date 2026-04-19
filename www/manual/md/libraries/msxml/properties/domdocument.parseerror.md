# DOMDocument.ParseError Property

Returns the ParseError object that describes the outcome of the last `LoadXML` or `Load` call.

## Access

Read-only.

## Type

ParseError object.

## Remarks

- This property always returns a ParseError object, even when parsing succeeded.
- After a successful parse, `ParseError.ErrorCode` is 0.
- After a failed parse, `ParseError` is populated with the error details, including `Reason`, `Line`, `LinePos`, and `SrcText`.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If Not oXML.LoadXML("<root><unclosed>") Then
    Response.Write "Error " & oXML.ParseError.ErrorCode & ": " & oXML.ParseError.Reason
    Response.Write " (Line " & oXML.ParseError.Line & ", Col " & oXML.ParseError.LinePos & ")"
End If
Set oXML = Nothing
%>
```