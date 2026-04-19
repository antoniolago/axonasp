# Recordset.Filter Property

Gets or sets a filter expression for visible rows in the recordset.

## Syntax

```asp
value = rs.Filter
rs.Filter = newFilter
```

## Return Value

String or Integer. Returns the current filter setting.

## Remarks

- Property names are case-insensitive.
- Filter syntax support depends on provider/runtime capabilities.
- Use simple predicates for maximum compatibility.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.Filter = "id = 1"
If Not rs.EOF Then Response.Write rs.Fields("name").Value

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```