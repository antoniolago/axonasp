# Command.CreateParameter Method

Creates a Parameter object that can be appended to the command Parameters collection.

## Syntax

```asp
Set param = cmd.CreateParameter(name, type, direction, size, value)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | No | Parameter name used for readability and provider mapping. |
| `type` | Integer | No | ADODB data type code. |
| `direction` | Integer | No | Direction flag: input, output, or input-output. |
| `size` | Integer | No | Maximum size in bytes or characters. |
| `value` | Variant | No | Initial parameter value. |

## Return Value

Parameter. Returns an ADODB.Parameter object.

## Remarks

- Method names are case-insensitive.
- Call `Parameters.Append` to attach the new parameter to the command.
- CreateParameter does not execute the command.
- Use this method to avoid string concatenation in SQL and improve input safety.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, p, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
cmd.ActiveConnection = conn
cmd.CommandText = "SELECT id, name FROM users WHERE id = ?"

Set p = cmd.CreateParameter("id", 3, 1, 4, 1)
cmd.Parameters.Append p

Set rs = cmd.Execute
If Not rs.EOF Then
    Response.Write rs.Fields("name").Value
End If

rs.Close
conn.Close
Set rs = Nothing
Set p = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```