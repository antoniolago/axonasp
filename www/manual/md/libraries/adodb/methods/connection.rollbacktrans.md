# Connection.RollbackTrans Method

Rolls back the active transaction and discards pending changes.

## Syntax

```asp
conn.RollbackTrans
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Call this method after `BeginTrans` when execution fails.
- Rollback restores the state from before transaction start.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

conn.BeginTrans
On Error Resume Next
conn.Execute "UPDATE users SET active = 0 WHERE id = 1"
If Err.Number <> 0 Then
    conn.RollbackTrans
    Response.Write "Transaction rolled back"
Else
    conn.CommitTrans
End If
On Error GoTo 0

conn.Close
Set conn = Nothing
%>
```