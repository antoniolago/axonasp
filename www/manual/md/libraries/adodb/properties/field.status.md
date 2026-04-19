# Field.Status Property

Returns status flags for the current field value.

## Syntax

```asp
value = rs.Fields("columnName").Status
```

## Return Value

Integer. Returns status information for the field according to provider/runtime flags.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Field status often reflects row update and null-state metadata.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

If Not rs.EOF Then Response.Write CStr(rs.Fields("name").Status)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```