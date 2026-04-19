# Recordset.ActiveConnection Property

Gets or sets the connection used by the recordset.

## Syntax

```asp
Set connRef = rs.ActiveConnection
Set rs.ActiveConnection = conn
```

## Return Value

Object. Returns an ADODB.Connection object reference.

## Remarks

- Property names are case-insensitive.
- Use `Set` for object assignment.
- Set before opening recordsets when source does not embed connection context.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, connRef

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = Server.CreateObject("ADODB.Recordset")
Set rs.ActiveConnection = conn
rs.Open "SELECT id, name FROM users", conn
Set connRef = rs.ActiveConnection

Response.Write "State: " & CStr(connRef.State)

rs.Close
conn.Close
Set connRef = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```