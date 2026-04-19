# Field.OriginalValue Property

Returns the original field value before local edits on the current row.

## Syntax

```asp
value = rs.Fields("columnName").OriginalValue
```

## Return Value

Variant. Returns the original value tracked by the runtime for the current row field.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- In providers without full change tracking, value can match `Field.Value`.

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
    Response.Write "Original: " & rs.Fields("name").OriginalValue & "<br>"
    rs.Fields("name").Value = "Temporary Change"
    Response.Write "Current: " & rs.Fields("name").Value
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```