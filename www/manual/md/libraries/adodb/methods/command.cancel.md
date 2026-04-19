# Command.Cancel Method

Cancels the current command execution.

## Syntax

```asp
cmd.Cancel
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Calling Cancel does not interrupt already completed operations.
- Use this method only for compatibility with scripts that expect the ADODB command surface.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
cmd.ActiveConnection = conn
cmd.CommandText = "SELECT id, name FROM users"

' Compatibility no-op in current runtime.
cmd.Cancel

Response.Write "Command.Cancel executed"

conn.Close
Set cmd = Nothing
Set conn = Nothing
%>
```