# Recordset.AbsolutePage Property

Gets or sets the current page number in paged recordset navigation.

## Syntax

```asp
page = rs.AbsolutePage
rs.AbsolutePage = newPage
```

## Return Value

Integer. Returns the current page index.

## Remarks

- Property names are case-insensitive.
- Page behavior depends on `PageSize` and provider support.
- Set `PageSize` before relying on page-based navigation.

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
Response.Write "Page: " & CStr(rs.AbsolutePage)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```