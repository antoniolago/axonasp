# Errors.Clear Method

Clears all error entries from the connection Errors collection.

## Syntax

```asp
conn.Errors.Clear
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Use Clear after handling errors to reset the collection state.
- Clear does not fix the source problem; it only removes stored error entries.
- The Errors collection belongs to the current Connection object.

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

Response.Write "Before clear: " & CStr(conn.Errors.Count) & "<br>"
conn.Errors.Clear
Response.Write "After clear: " & CStr(conn.Errors.Count)

conn.Close
Set conn = Nothing
%>
```