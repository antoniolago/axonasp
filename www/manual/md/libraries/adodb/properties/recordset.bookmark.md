# Recordset.Bookmark Property

Gets or sets a bookmark that identifies the current row position.

## Syntax

```asp
bm = rs.Bookmark
rs.Bookmark = bm
```

## Return Value

Variant. Returns the bookmark token for the current row.

## Remarks

- Property names are case-insensitive.
- Bookmark support depends on cursor/provider capabilities.
- Save bookmark values to return to a previously visited row.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, bm

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

If Not rs.EOF Then
    bm = rs.Bookmark
    rs.MoveNext
    rs.Bookmark = bm
    Response.Write rs.Fields("name").Value
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```