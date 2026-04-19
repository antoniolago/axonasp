# Errors.Count Property

Returns the number of error entries stored in the connection Errors collection.

## Syntax

```asp
count = conn.Errors.Count
```

## Return Value

Integer. Returns the number of ADODB.Error items in the Errors collection.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- The value is `0` when no errors are present.
- The value increases when operations fail and add entries to the Errors collection.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

On Error Resume Next
conn.Execute "SELECT * FROM table_that_does_not_exist"
On Error GoTo 0

Response.Write "Errors count: " & CStr(conn.Errors.Count)

conn.Close
Set conn = Nothing
%>
```