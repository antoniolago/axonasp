# Parameters.Count Method

Returns the number of Parameter objects in the command Parameters collection.

## Syntax

```asp
count = cmd.Parameters.Count
```

## Parameters

No parameters.

## Return Value

Integer. Returns the number of parameters currently appended to the command.

## Remarks

- Method names are case-insensitive.
- Use Count to validate parameter setup before Execute.
- Count reflects only parameters explicitly appended in the current command object.
- Parameter order matters for positional placeholders.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, p

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
cmd.CommandText = "SELECT id FROM users WHERE id = ?"

Set p = cmd.CreateParameter("id", 3, 1, 4, 1)
cmd.Parameters.Append p

Response.Write "Parameters count: " & CStr(cmd.Parameters.Count)

conn.Close
Set p = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```