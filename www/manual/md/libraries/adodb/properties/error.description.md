# Error.Description Property

Returns the human-readable message text for an ADODB error entry.

## Syntax

```asp
text = errObj.Description
```

## Return Value

String. Returns the error description message.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use Description in logs or user-safe diagnostics.
- Pair with Number and SQLState for complete error context.

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
	Response.Write "Error description: " & errObj.Description
End If

conn.Close
Set errObj = Nothing
Set conn = Nothing
%>
```