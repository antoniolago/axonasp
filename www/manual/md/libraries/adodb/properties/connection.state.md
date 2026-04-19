# Connection.State Property

Returns the current open/closed state of the connection.

## Syntax

```asp
state = conn.State
```

## Return Value

Integer. Returns `0` when closed and `1` when open.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Check this value before operations that require an open connection.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
Response.Write "Before open: " & CStr(conn.State) & "<br>"

conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Response.Write "After open: " & CStr(conn.State) & "<br>"

conn.Close
Response.Write "After close: " & CStr(conn.State)

Set conn = Nothing
%>
```