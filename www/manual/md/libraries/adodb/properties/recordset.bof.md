# Recordset.BOF Property

Indicates whether the cursor is before the first row.

## Syntax

```asp
flag = rs.BOF
```

## Return Value

Boolean. Returns True when cursor is before the first row; otherwise False.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use together with EOF to detect empty rowsets.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

Response.Write "BOF: " & CStr(rs.BOF)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```