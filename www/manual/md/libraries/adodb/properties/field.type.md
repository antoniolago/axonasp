# Field.Type Property

Returns the ADODB data type code for the field.

## Syntax

```asp
typeCode = rs.Fields("columnName").Type
```

## Return Value

Integer. Returns the ADODB type constant for the column.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use Type to apply safe conversion logic when processing dynamic schemas.
- Type values depend on provider mappings.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
If Not rs.EOF Then
	Response.Write "id type: " & CStr(rs.Fields("id").Type) & "<br>"
	Response.Write "name type: " & CStr(rs.Fields("name").Type)
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```