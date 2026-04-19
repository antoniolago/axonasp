# Field.Precision Property

Returns numeric precision metadata for the field.

## Syntax

```asp
value = rs.Fields("columnName").Precision
```

## Return Value

Integer. Returns declared precision for numeric columns; provider-specific fallback may apply.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use with `NumericScale` to validate decimal handling.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT price FROM products")

If Not rs.EOF Then Response.Write CStr(rs.Fields("price").Precision)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```