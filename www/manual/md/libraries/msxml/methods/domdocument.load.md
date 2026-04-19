# DOMDocument.Load Method

Loads an XML document from a file path or HTTP/HTTPS URL.

## Syntax

```asp
bSuccess = objXML.Load(url)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `url` | String | Yes | An HTTP or HTTPS URL, or a relative or absolute file path resolved via `Server.MapPath`. |

## Return Value

Boolean. Returns True if the document was loaded and parsed successfully. Returns False on a network failure, file-not-found error, or invalid XML. `ParseError.ErrorCode` is set to the HTTP status code on HTTP failures, or -1 for file/parse failures.

## Remarks

- HTTP and HTTPS requests use a 30-second timeout.
- File paths are resolved using `Server.MapPath` from the currently executing page context.
- Calling `Load` replaces any previously loaded or built document.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If oXML.Load("https://example.com/feed.xml") Then
    Response.Write "Loaded: " & oXML.DocumentElement.NodeName
Else
    Response.Write "Failed: " & oXML.ParseError.Reason
End If
Set oXML = Nothing
%>
```