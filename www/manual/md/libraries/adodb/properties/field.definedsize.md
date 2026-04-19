# Field.DefinedSize Property

Returns the declared maximum size for the field in the schema.

## Syntax

```asp
size = rs.Fields("columnName").DefinedSize
```

## Return Value

Integer. Returns the column size declared by schema metadata.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- DefinedSize is metadata; it does not depend on current row value.
- Compare with ActualSize to evaluate truncation risk.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT name FROM users")
If Not rs.EOF Then
	Response.Write "Defined size: " & CStr(rs.Fields("name").DefinedSize)
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```