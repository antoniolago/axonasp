# Connection.CommitTrans Method

Commits the current transaction and persists all pending changes.

## Syntax

```asp
conn.CommitTrans
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Call this method after a successful `BeginTrans` block.
- After commit, changes cannot be rolled back.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

conn.BeginTrans
conn.Execute "UPDATE users SET active = 1 WHERE id = 1"
conn.CommitTrans

Response.Write "Transaction committed"

conn.Close
Set conn = Nothing
%>
```