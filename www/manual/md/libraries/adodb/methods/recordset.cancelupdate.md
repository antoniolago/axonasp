# Recordset.CancelUpdate Method

Cancels pending edits on the current row before they are persisted.

## Syntax

```asp
rs.CancelUpdate
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Use CancelUpdate after modifying fields or calling AddNew when you want to discard changes.
- CancelUpdate affects only the current pending row change.
- After CancelUpdate, field values revert to the previously committed state.

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
    rs.Fields("name").Value = "Temporary Name"
    rs.CancelUpdate
    Response.Write "Update canceled"
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```