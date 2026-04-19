# Recordset.Resync Method

Refreshes the current row values from the data source.

## Syntax

```asp
rs.Resync
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Use it to keep compatibility with legacy scripts that call Resync.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
rs.Resync

Response.Write "Resync executed"

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```