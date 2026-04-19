# Connection.Errors Property

Returns the Errors collection associated with the connection.

## Syntax

```asp
Set errs = conn.Errors
```

## Return Value

Object. Returns an ADODB.Errors collection object.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use `Errors.Count`, `Errors.Item`, and `Errors.Clear` to inspect and manage error entries.
- The collection is updated after failed connection and command operations.

## Code Example

```asp
<%
Option Explicit
Dim conn, errs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

On Error Resume Next
conn.Execute "SELECT * FROM table_that_does_not_exist"
On Error GoTo 0

Set errs = conn.Errors
Response.Write "Errors count: " & CStr(errs.Count)

conn.Close
Set errs = Nothing
Set conn = Nothing
%>
```