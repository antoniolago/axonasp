# Command.CommandTimeout Property

Gets or sets the maximum execution time for the command, in seconds.

## Syntax

```asp
seconds = cmd.CommandTimeout
cmd.CommandTimeout = 30
```

## Return Value

Integer. Returns the configured timeout value in seconds.

## Remarks

- Property names are case-insensitive.
- Use this property to prevent long-running commands from blocking request execution.
- Set before calling Execute.
- Provider behavior can vary when timeout is `0` (infinite or provider default).

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
cmd.CommandText = "SELECT id FROM users"
cmd.CommandTimeout = 15

Response.Write "Timeout: " & CStr(cmd.CommandTimeout) & " seconds"

conn.Close
Set cmd = Nothing
Set conn = Nothing
%>
```