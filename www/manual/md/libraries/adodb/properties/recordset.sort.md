# Recordset.Sort Property

Gets or sets the sort expression applied to recordset rows.

## Syntax

```asp
value = rs.Sort
rs.Sort = "columnName ASC"
```

## Return Value

String. Returns the current sort expression.

## Remarks

- Property names are case-insensitive.
- Sort expression format is provider/runtime dependent.
- Use valid field names present in the recordset schema.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.Sort = "name ASC"
Response.Write rs.Sort

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```