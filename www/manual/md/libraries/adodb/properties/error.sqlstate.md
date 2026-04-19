# Error.SQLState Property

Returns the SQLSTATE code reported by the data provider.

## Syntax

```asp
state = errObj.SQLState
```

## Return Value

String. Returns the SQLSTATE code when available; can be an empty string for provider errors without SQLSTATE.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- SQLState helps classify errors in a provider-neutral format.
- Not all providers populate SQLState for every error type.

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
	Response.Write "SQLState: " & errObj.SQLState
End If

conn.Close
Set errObj = Nothing
Set conn = Nothing
%>
```