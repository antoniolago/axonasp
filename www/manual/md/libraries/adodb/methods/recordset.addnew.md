# Recordset.AddNew Method

Creates a new pending row in the current recordset.

## Syntax

```asp
rs.AddNew
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Set field values after AddNew and call `Update` to persist.
- Use `CancelUpdate` to discard pending row changes.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT * FROM users")
rs.AddNew
rs.Fields("name").Value = "New User"
rs.Update

Response.Write "Row added"

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```