# Recordset.Requery Method

Re-executes the original query and refreshes the recordset rows.

## Syntax

```asp
rs.Requery
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Requery uses the recordset source and active connection currently associated with the recordset.
- Cursor position can change after refresh.
- Use Requery when underlying table data may have changed.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = Server.CreateObject("ADODB.Recordset")
rs.Open "SELECT id, name FROM users", conn

Response.Write "Before requery count: " & CStr(rs.RecordCount) & "<br>"
rs.Requery
Response.Write "After requery count: " & CStr(rs.RecordCount)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```