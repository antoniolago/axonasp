# Field.Value Property

Gets or sets the current value of a column in the active row.

## Syntax

```asp
value = rs.Fields("columnName").Value
rs.Fields("columnName").Value = newValue
```

## Return Value

Variant. Returns the current field value for the active row. Returns `Null` when the database value is null.

## Remarks

- Property names are case-insensitive.
- Assigning to `Field.Value` marks the current row as edited.
- Call `Recordset.Update` to persist assigned values.
- Type conversion follows provider and ADODB coercion rules.

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
	Response.Write "Current name: " & rs.Fields("name").Value & "<br>"
	rs.Fields("name").Value = "Updated Name"
	rs.Update
	Response.Write "Name updated"
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```