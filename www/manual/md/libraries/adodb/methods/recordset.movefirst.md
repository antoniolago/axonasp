# Recordset.MoveFirst Method

Moves the cursor to the first row.

## Syntax

```asp
rs.MoveFirst
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Use this method to reset iteration to row 1.
- BOF becomes False when positioned on a valid first row.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
rs.MoveLast
rs.MoveFirst

If Not rs.EOF Then Response.Write rs.Fields("name").Value

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```