# Recordset.Close Method

Closes the recordset and releases cursor resources.

## Syntax

```asp
rs.Close
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Call this method before closing the parent connection.
- After close, `State` becomes `0`.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id FROM users")
rs.Close

Response.Write "Recordset state: " & CStr(rs.State)

conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```