# Recordset.GetRows Method

Returns recordset rows as a two-dimensional array.

## Syntax

```asp
rows = rs.GetRows
```

## Parameters

No parameters.

## Return Value

Array or Empty. Returns a 2D array in `[columnIndex][rowIndex]` order. Returns Empty when the recordset is closed or has no rows.

## Remarks

- Method names are case-insensitive.
- This method reads the full remaining rowset into memory.
- Use for bulk processing when array access is preferred.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, rows, i

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
rows = rs.GetRows

If IsArray(rows) Then
    For i = 0 To UBound(rows, 2)
        Response.Write rows(0, i) & " - " & rows(1, i) & "<br>"
    Next
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```