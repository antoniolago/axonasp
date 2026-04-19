# Connection.Close Method

Closes an open connection and releases provider resources.

## Syntax

```asp
conn.Close
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Call this method when all recordsets are closed.
- After closing, `State` becomes `0`.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Response.Write "Opened<br>"
conn.Close
Response.Write "Closed"

Set conn = Nothing
%>
```