# Recordset.EditMode Property

Returns the current edit state for the active row.

## Syntax

```asp
value = rs.EditMode
```

## Return Value

Integer. Returns edit mode flag (for example, not editing, editing, or add-new state).

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use to detect pending edits before `Update` or `CancelUpdate`.

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
    Response.Write "Before: " & CStr(rs.EditMode) & "<br>"
    rs.Fields("name").Value = "Temp"
    Response.Write "After: " & CStr(rs.EditMode)
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```