# Field.Attributes Property

Returns the attribute flags for the field metadata.

## Syntax

```asp
flags = rs.Fields("columnName").Attributes
```

## Return Value

Integer. Returns a bitmask describing field capabilities and metadata flags.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Flag values are provider-dependent.
- Common uses include checking nullable and auto-increment behavior.

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
	Response.Write "Field attributes: " & CStr(rs.Fields("id").Attributes)
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```