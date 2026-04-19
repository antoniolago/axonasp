# DOMDocument.LoadXML Method

Parses an XML string and loads it into the document object.

## Syntax

```asp
bSuccess = objXML.LoadXML(xmlString)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `xmlString` | String | Yes | A well-formed XML string to parse. |

## Return Value

Boolean. Returns True if the XML was parsed successfully. Returns False if the string is empty, Null, or contains invalid XML. Check `ParseError.ErrorCode` for details on failure.

## Remarks

- On a failed parse, `ParseError` is populated with the error code, reason, and the source position where the parse stopped.
- Calling `LoadXML` replaces any previously loaded or built document.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If oXML.LoadXML("<catalog><item>First</item><item>Second</item></catalog>") Then
    Dim oRoot
    Set oRoot = oXML.DocumentElement
    Response.Write "Root: " & oRoot.NodeName
Else
    Response.Write "Parse error: " & oXML.ParseError.Reason
End If
Set oXML = Nothing
%>
```