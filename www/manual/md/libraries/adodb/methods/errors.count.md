# Errors.Count Method

Returns the number of error objects in the Errors collection.

## Syntax

```asp
count = conn.Errors.Count
```

## Parameters

No parameters.

## Return Value

Integer. Returns the number of errors currently stored in the connection Errors collection.

## Remarks

- Method names are case-insensitive.
- The Errors collection is associated with a Connection object.
- The count increases when an operation fails and adds an ADODB.Error item.
- Call `Errors.Clear` to reset the collection.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

' Force an error to populate Errors collection.
On Error Resume Next
conn.Execute "SELECT * FROM table_that_does_not_exist"
On Error GoTo 0

Response.Write "Errors count: " & CStr(conn.Errors.Count)

conn.Close
Set conn = Nothing
%>
```