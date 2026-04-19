# Command.Execute Method

Executes the statement configured in `CommandText` using the command connection and parameters.

## Syntax

```asp
result = cmd.Execute
```

## Parameters

No parameters.

## Return Value

Variant. Returns an ADODB.Recordset for query statements. Returns an Integer with affected rows for action statements. Returns Empty when execution fails.

## Remarks

- Method names are case-insensitive.
- Set `ActiveConnection` and `CommandText` before calling this method.
- Use `CreateParameter` and `Parameters.Append` to pass values safely.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, result

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
cmd.CommandText = "SELECT id, name FROM users"

Set result = cmd.Execute
If Not result.EOF Then
    Response.Write result.Fields("name").Value
End If

result.Close
conn.Close
Set result = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```