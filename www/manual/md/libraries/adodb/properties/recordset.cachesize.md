# Recordset.CacheSize Property

Gets or sets the number of rows cached locally for cursor operations.

## Syntax

```asp
value = rs.CacheSize
rs.CacheSize = newValue
```

## Return Value

Integer. Returns configured cache size.

## Remarks

- Property names are case-insensitive.
- Set before heavy navigation workloads.
- Effective behavior can depend on provider cursor implementation.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.CacheSize = 25
Response.Write CStr(rs.CacheSize)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```