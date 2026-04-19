# Field.ActualSize Property

Returns the actual size of the current field value.

## Syntax

```asp
length = rs.Fields("columnName").ActualSize
```

## Return Value

Integer. Returns the current value length in characters for text data, or byte-length semantics as provided by the driver for binary-like values.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- ActualSize reflects the current row value, not the schema maximum.
- Use DefinedSize for declared column capacity.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT name FROM users WHERE id = 1")
If Not rs.EOF Then
	Response.Write "Actual size: " & CStr(rs.Fields("name").ActualSize)
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```