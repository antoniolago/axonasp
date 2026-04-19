# Recordset.Status Property

Returns or sets record status flags for the current row context.

## Syntax

```asp
value = rs.Status
rs.Status = newStatus
```

## Return Value

Integer. Returns record status bit flags.

## Remarks

- Property names are case-insensitive.
- Status values are provider/runtime dependent.
- Use for advanced state inspection in update workflows.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

If Not rs.EOF Then Response.Write CStr(rs.Status)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```