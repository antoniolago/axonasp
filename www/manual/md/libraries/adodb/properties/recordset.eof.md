# Recordset.EOF Property

Indicates whether the cursor is positioned after the last row.

## Syntax

```asp
eofFlag = rs.EOF
```

## Return Value

Boolean. Returns True when cursor is beyond the final row; otherwise False.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Combine with BOF to detect empty result sets.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

Do While Not rs.EOF
    Response.Write rs.Fields("name").Value & "<br>"
    rs.MoveNext
Loop

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```