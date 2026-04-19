# Recordset.RecordCount Property

Returns the number of rows currently represented by the recordset.

## Syntax

```asp
count = rs.RecordCount
```

## Return Value

Integer. Returns row count, or provider-specific fallback when exact count is unavailable.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Some cursor/provider combinations may require movement to finalize count.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

Response.Write CStr(rs.RecordCount)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```