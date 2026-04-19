# Recordset.PageCount Property

Returns the total number of pages based on row count and page size.

## Syntax

```asp
value = rs.PageCount
```

## Return Value

Integer. Returns computed total pages.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Depends on `PageSize` and row materialization state.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.PageSize = 10
Response.Write CStr(rs.PageCount)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```