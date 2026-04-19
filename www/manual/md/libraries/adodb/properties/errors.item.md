# Errors.Item Property

Returns an error object from the Errors collection by index.

## Syntax

```asp
Set errObj = conn.Errors.Item(index)
```

## Return Value

Object or Empty. Returns an ADODB.Error object for a valid index, or Empty for out-of-range index access.

## Remarks

- Property names are case-insensitive.
- Use `Errors.Count` before reading an item.
- Error objects expose `Number`, `Description`, `Source`, and `SQLState`.

## Code Example

```asp
<%
Option Explicit
Dim conn, errObj

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

On Error Resume Next
conn.Execute "SELECT * FROM table_that_does_not_exist"
On Error GoTo 0

If conn.Errors.Count > 0 Then
    Set errObj = conn.Errors.Item(0)
    Response.Write errObj.Description
End If

conn.Close
Set errObj = Nothing
Set conn = Nothing
%>
```