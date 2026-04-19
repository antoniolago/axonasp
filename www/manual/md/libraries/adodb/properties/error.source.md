# Error.Source Property

Returns the component or method name that raised the ADODB error.

## Syntax

```asp
name = errObj.Source
```

## Return Value

String. Returns the error source text.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Source can help identify whether the fault came from SQL, provider, or command routing.
- Combine with Number and Description for full diagnostics.

## Code Example

```asp
<%
Option Explicit
Dim conn, errObj

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

On Error Resume Next
conn.Execute "SELECT * FROM table_that_does_not_exist"
On Error GoTo 0

If conn.Errors.Count > 0 Then
	Set errObj = conn.Errors.Item(0)
	Response.Write "Error source: " & errObj.Source
End If

conn.Close
Set errObj = Nothing
Set conn = Nothing
%>
```