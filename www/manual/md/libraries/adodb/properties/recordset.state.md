# Recordset.State Property

Returns the open/closed state of the recordset.

## Syntax

```asp
value = rs.State
```

## Return Value

Integer. Returns `0` when closed and `1` when open.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Check before reading fields or moving the cursor.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
Response.Write "Open state: " & CStr(rs.State) & "<br>"

rs.Close
Response.Write "Closed state: " & CStr(rs.State)

conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```