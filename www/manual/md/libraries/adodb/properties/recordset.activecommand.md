# Recordset.ActiveCommand Property

Returns or sets the command object associated with the recordset.

## Syntax

```asp
Set cmdRef = rs.ActiveCommand
Set rs.ActiveCommand = cmd
```

## Return Value

Object. Returns an ADODB.Command reference when available.

## Remarks

- Property names are case-insensitive.
- Use `Set` for assignment and retrieval.
- This association is useful for introspection of command-driven recordsets.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, rs, cmdRef

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
cmd.CommandText = "SELECT id, name FROM users"
Set rs = cmd.Execute
Set cmdRef = rs.ActiveCommand

If IsObject(cmdRef) Then Response.Write "ActiveCommand available"

rs.Close
conn.Close
Set cmdRef = Nothing
Set rs = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```