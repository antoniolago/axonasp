# Connection.Open Method

Opens the database connection using the configured connection string.

## Syntax

```asp
conn.Open [connectionString]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `connectionString` | String | No | Overrides `ConnectionString` for this call. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- If no parameter is provided, `ConnectionString` must already be set.
- After a successful call, `State` becomes `1`.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Response.Write "State: " & CStr(conn.State)

conn.Close
Set conn = Nothing
%>
```