# Connection.Execute Method

Executes a SQL statement directly on the connection.

## Syntax

```asp
result = conn.Execute(commandText)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `commandText` | String | Yes | SQL statement to run. |

## Return Value

Variant. Returns an ADODB.Recordset for query statements. Returns an Integer for affected rows in action statements. Returns Empty on failure.

## Remarks

- Method names are case-insensitive.
- Query detection is based on SQL statement type in the runtime.
- Use this method for quick execution when a dedicated Command object is not needed.

## Code Example

```asp
<%
Option Explicit
Dim conn, result

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set result = conn.Execute("SELECT id, name FROM users")
If Not result.EOF Then
    Response.Write result.Fields("name").Value
End If

result.Close
conn.Close
Set result = Nothing
Set conn = Nothing
%>
```