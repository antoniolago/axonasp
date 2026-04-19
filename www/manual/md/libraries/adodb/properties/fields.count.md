# Fields.Count Property

Returns the number of fields in the current Fields collection.

## Syntax

```asp
count = rs.Fields.Count
```

## Return Value

Integer. Returns total field entries in the collection.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use with indexed `Fields.Item(i)` loops.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

Response.Write CStr(rs.Fields.Count)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```