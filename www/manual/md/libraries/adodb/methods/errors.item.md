# Errors.Item Method

Returns an Error object from the Errors collection by index.

## Syntax

```asp
Set errObj = conn.Errors.Item(index)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `index` | Integer | Yes | Zero-based index of the error item in the collection. |

## Return Value

Error or Empty. Returns an ADODB.Error object for a valid index, or Empty when the index is out of range.

## Remarks

- Method names are case-insensitive.
- Use `Errors.Count` to validate the index before calling Item.
- Error objects expose Number, Description, Source, and SQLState.
- The Errors collection belongs to the Connection object.

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
    Response.Write "Error " & CStr(errObj.Number) & ": " & errObj.Description
End If

conn.Close
Set errObj = Nothing
Set conn = Nothing
%>
```