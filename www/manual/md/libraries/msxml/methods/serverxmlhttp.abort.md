# ServerXMLHTTP.Abort Method

Cancels the current HTTP request immediately without waiting for a response.

## Syntax

```asp
objHTTP.Abort
```

## Parameters

None.

## Return Value

Empty. This method does not return a value.

## Remarks

- Calling `Abort` sets `ReadyState` to 4 without populating any response properties.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/large-file", False
On Error Resume Next
oHTTP.Abort
On Error GoTo 0
Set oHTTP = Nothing
%>
```