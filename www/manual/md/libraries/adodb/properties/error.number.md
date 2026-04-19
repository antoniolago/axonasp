# Error.Number Property

Returns the numeric error code for an ADODB error entry.

## Syntax

```asp
code = errObj.Number
```

## Return Value

Integer. Returns the provider or runtime-specific error number.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use Number together with Description for diagnostics.
- Values are typically aligned with provider HRESULT-style errors.

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
	Response.Write "Error number: " & CStr(errObj.Number)
End If

conn.Close
Set errObj = Nothing
Set conn = Nothing
%>
```