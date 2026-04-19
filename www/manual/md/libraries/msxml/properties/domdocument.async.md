# DOMDocument.Async Property

Gets or sets whether the document loads asynchronously.

## Access

Read/Write.

## Type

Boolean.

## Default

False.

## Remarks

- This property is accepted for compatibility with existing code. The current AxonASP implementation always loads documents synchronously regardless of this setting.
- Set to False before calling `Load` or `LoadXML` to follow the Classic ASP convention.

## Code Example

```asp
<%
Dim oXML
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.Async = False
oXML.LoadXML "<data/>"
Response.Write oXML.DocumentElement.NodeName
Set oXML = Nothing
%>
```