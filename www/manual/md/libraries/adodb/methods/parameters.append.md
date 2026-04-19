# Parameters.Append Method

Adds a Parameter object to the command Parameters collection.

## Syntax

```asp
cmd.Parameters.Append parameterObj
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `parameterObj` | Parameter | Yes | Parameter object created by `CreateParameter`. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Append adds the parameter to the end of the collection.
- Parameter order must match placeholder order for positional providers.
- Append does not execute the command.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, p

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
cmd.ActiveConnection = conn
cmd.CommandText = "SELECT id, name FROM users WHERE id = ?"

Set p = cmd.CreateParameter("id", 3, 1, 4, 1)
cmd.Parameters.Append p

Response.Write "Parameters count: " & CStr(cmd.Parameters.Count)

conn.Close
Set p = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```