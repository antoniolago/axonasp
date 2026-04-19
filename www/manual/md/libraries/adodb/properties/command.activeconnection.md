# Command.ActiveConnection Property

Gets or sets the Connection object used by the command.

## Syntax

```asp
Set connRef = cmd.ActiveConnection
Set cmd.ActiveConnection = conn
```

## Return Value

Object. Returns an ADODB.Connection object reference.

## Remarks

- Property names are case-insensitive.
- Use `Set` when assigning or reading this object property.
- This property must be set before calling `Command.Execute`.
- Reassigning ActiveConnection changes the connection target for future executions.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, connRef

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
Set connRef = cmd.ActiveConnection

Response.Write "Connection state: " & CStr(connRef.State)

conn.Close
Set connRef = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```