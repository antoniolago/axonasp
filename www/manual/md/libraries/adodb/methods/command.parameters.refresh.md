# Command.Parameters.Refresh Method

Refreshes the command parameter metadata from the provider.

## Syntax

```asp
cmd.Parameters.Refresh
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Use explicit `CreateParameter` and `Parameters.Append` when defining parameters.
- Call this method only for compatibility with existing scripts.

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
cmd.CommandText = "SELECT id FROM users WHERE id = ?"

' Compatibility no-op in current runtime.
cmd.Parameters.Refresh

Response.Write "Parameters.Refresh executed"

conn.Close
Set cmd = Nothing
Set conn = Nothing
%>
```