# Recordset.Index Property

Gets or sets the active index name used by seek operations.

## Syntax

```asp
value = rs.Index
rs.Index = newIndex
```

## Return Value

String. Returns the current index name.

## Remarks

- Property names are case-insensitive.
- Set this before calling `Recordset.Seek` when index-based navigation is needed.
- Provider support for named indexes can vary.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.Index = "id"
Response.Write rs.Index

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```