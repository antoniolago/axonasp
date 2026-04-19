# Recordset.MoveNext Method

Moves the cursor to the next row.

## Syntax

```asp
rs.MoveNext
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- EOF becomes True when the cursor moves past the last row.
- Use this in forward iteration loops.

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