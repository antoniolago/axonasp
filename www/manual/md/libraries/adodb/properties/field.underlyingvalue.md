# Field.UnderlyingValue Property

Returns the underlying provider value for the current field.

## Syntax

```asp
value = rs.Fields("columnName").UnderlyingValue
```

## Return Value

Variant. Returns the provider-level underlying value for the current row field.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- For providers without separate change-tracking layers, value can match `Field.Value`.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT name FROM users WHERE id = 1")

If Not rs.EOF Then Response.Write rs.Fields("name").UnderlyingValue

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```