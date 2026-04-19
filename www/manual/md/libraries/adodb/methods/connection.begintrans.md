# Connection.BeginTrans Method

Starts a transaction on the current connection.

## Syntax

```asp
level = conn.BeginTrans
```

## Parameters

No parameters.

## Return Value

Integer. Returns `1` when the transaction starts successfully; returns `0` otherwise.

## Remarks

- Method names are case-insensitive.
- Pair this method with `CommitTrans` or `RollbackTrans`.
- Use transactions when multiple statements must succeed or fail together.

## Code Example

```asp
<%
Option Explicit
Dim conn, level

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

level = conn.BeginTrans
If level = 1 Then
    conn.Execute "UPDATE users SET active = 1 WHERE id = 1"
    conn.CommitTrans
    Response.Write "Committed"
Else
    Response.Write "Transaction not started"
End If

conn.Close
Set conn = Nothing
%>
```