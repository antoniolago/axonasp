# Recordset.Update Method

Persists pending edits for the current row.

## Syntax

```asp
rs.Update
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Use after `AddNew` or field value changes.
- Requires an updatable recordset and valid connection context.

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
    rs.Fields("name").Value = "Updated Name"
    rs.Update
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```