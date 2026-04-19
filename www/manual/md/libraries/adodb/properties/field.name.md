# Field.Name Property

Returns the column name represented by the Field object.

## Syntax

```asp
name = rs.Fields(index).Name
```

## Return Value

String. Returns the field name from the recordset schema.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Name reflects the alias when SQL uses `AS`.
- Use Name to build dynamic table headers and field maps.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, i

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name, email FROM users")
For i = 0 To rs.Fields.Count - 1
	Response.Write "Field " & CStr(i) & ": " & rs.Fields(i).Name & "<br>"
Next

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```