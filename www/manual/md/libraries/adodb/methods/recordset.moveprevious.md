# Recordset.MovePrevious Method

Moves the cursor to the previous row in the result set.

## Syntax

```asp
rs.MovePrevious
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- After calling MovePrevious, check BOF to verify whether the cursor moved before the first row.
- Calling MovePrevious on the first row sets BOF to True.
- Use MovePrevious only with cursor types that support backward navigation.

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
Response.Write "Last row: " & rs.Fields("name").Value & "<br>"

rs.MovePrevious
If Not rs.BOF Then
    Response.Write "Previous row: " & rs.Fields("name").Value
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```