# Recordset.AbsolutePosition Property

Gets or sets the current row position in the recordset.

## Syntax

```asp
pos = rs.AbsolutePosition
rs.AbsolutePosition = newPos
```

## Return Value

Integer. Returns the current one-based row position.

## Remarks

- Property names are case-insensitive.
- Position support depends on cursor type/provider behavior.
- Assigning out-of-range values can move cursor to BOF/EOF boundaries.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.MoveFirst
Response.Write "Position: " & CStr(rs.AbsolutePosition)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```