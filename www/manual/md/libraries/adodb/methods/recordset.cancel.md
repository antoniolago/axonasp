# Recordset.Cancel Method

Cancels the current recordset operation.

## Syntax

```asp
rs.Cancel
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Use this method only to preserve compatibility with legacy scripts.
- It does not close the recordset or revert changes.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")

' Compatibility no-op in current runtime.
rs.Cancel

Response.Write "Recordset.Cancel executed"

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```