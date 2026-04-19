# Recordset.UpdateBatch Method

Applies pending batch updates to the data source.

## Syntax

```asp
rs.UpdateBatch
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Keep this call for legacy scripts that use batch update flow.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.UpdateBatch
Response.Write "UpdateBatch executed"

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```