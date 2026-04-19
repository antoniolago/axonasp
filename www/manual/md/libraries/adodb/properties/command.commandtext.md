# Command.CommandText Property

Gets or sets the SQL statement or stored procedure name executed by the command.

## Syntax

```asp
sql = cmd.CommandText
cmd.CommandText = "SELECT id, name FROM users"
```

## Return Value

String. Returns the current command text.

## Remarks

- Property names are case-insensitive.
- Set CommandText before calling Execute.
- For parameterized statements, use placeholders and append parameters in the same order.
- CommandText can contain SELECT, INSERT, UPDATE, DELETE, or provider-supported statements.

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

Response.Write "Command text: " & cmd.CommandText

conn.Close
Set cmd = Nothing
Set conn = Nothing
%>
```