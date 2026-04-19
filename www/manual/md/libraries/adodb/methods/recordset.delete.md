# Recordset.Delete Method

Deletes the current row from the recordset and data source.

## Syntax

```asp
rs.Delete
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Deletion applies to the current row position.
- Move to the next valid row after deletion when iterating.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT * FROM users WHERE id = 1")
If Not rs.EOF Then
    rs.Delete
    Response.Write "Row deleted"
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```