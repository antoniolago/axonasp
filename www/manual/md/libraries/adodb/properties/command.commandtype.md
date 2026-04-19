# Command.CommandType Property

Gets or sets how CommandText should be interpreted.

## Syntax

```asp
kind = cmd.CommandType
cmd.CommandType = 1
```

## Return Value

Integer. Returns the command type flag.

## Remarks

- Property names are case-insensitive.
- Common values are `1` for text command and `4` for stored procedure.
- Use `1` for SQL text in most AxonASP ADODB scenarios.
- Set CommandType before Execute for predictable provider behavior.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
cmd.CommandType = 1
cmd.CommandText = "SELECT COUNT(*) AS total FROM users"

Response.Write "CommandType: " & CStr(cmd.CommandType)

conn.Close
Set cmd = Nothing
Set conn = Nothing
%>
```