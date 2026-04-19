# Recordset.CancelBatch Method

Cancels pending batch updates in a batch-update workflow.

## Syntax

```asp
rs.CancelBatch
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Use this method for script compatibility when batch mode is not required.
- For current behavior, pending edits are managed with AddNew/Update/CancelUpdate.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT * FROM users")

' Compatibility no-op in current runtime.
rs.CancelBatch

Response.Write "Recordset.CancelBatch executed"

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```