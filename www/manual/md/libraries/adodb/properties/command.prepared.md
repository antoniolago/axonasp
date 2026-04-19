# Command.Prepared Property

Gets or sets whether the command should be prepared before execution.

## Syntax

```asp
isPrepared = cmd.Prepared
cmd.Prepared = True
```

## Return Value

Boolean. Returns True when prepared mode is enabled; otherwise False.

## Remarks

- Property names are case-insensitive.
- Prepared mode can improve performance for repeated command execution.
- Some providers may ignore this hint.
- Set this property before the first Execute call.

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
cmd.CommandText = "SELECT id, name FROM users WHERE active = 1"
cmd.Prepared = True

Response.Write "Prepared: " & CStr(cmd.Prepared)

conn.Close
Set cmd = Nothing
Set conn = Nothing
%>
```