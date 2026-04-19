# Field.NumericScale Property

Gets or sets the number of decimal places for numeric field values.

## Syntax

```asp
scale = rs.Fields("amount").NumericScale
rs.Fields("amount").NumericScale = 2
```

## Return Value

Integer. Returns the numeric scale for the field.

## Remarks

- Property names are case-insensitive.
- Some providers expose this as read-only metadata.
- When writable, set before persisting values that require precision control.
- For non-numeric fields, value can be zero or provider-specific.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT price FROM products")
If Not rs.EOF Then
	Response.Write "Numeric scale: " & CStr(rs.Fields("price").NumericScale)
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```