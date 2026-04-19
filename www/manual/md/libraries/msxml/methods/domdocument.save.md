# DOMDocument.Save Method

Serializes the document and writes it to a file at the specified path.

## Syntax

```asp
bSuccess = objXML.Save(filename)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `filename` | String | Yes | An absolute or relative file path to write the XML to. |

## Return Value

Boolean. Returns True if the file was written successfully. Returns False if the document has no content, the context is unavailable, or the file write fails.

## Remarks

- The file is written with UTF-8 encoding.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<data><entry>Test</entry></data>"
If oXML.Save(Server.MapPath("output.xml")) Then
    Response.Write "Saved."
Else
    Response.Write "Save failed."
End If
Set oXML = Nothing
%>
```