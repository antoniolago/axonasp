# Recordset.Find Method

Searches the recordset for the next row that matches a criteria expression.

## Syntax

```asp
rs.Find criteria
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `criteria` | String | Yes | Match expression, such as `"id = 10"` or `"name = 'Ana'"`. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Find moves the current cursor position to the first matching row at or after the current position.
- If no row matches, EOF becomes True.
- Criteria parsing supports the runtime-compatible subset used by AxonASP ADODB.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
rs.Find "id = 1"

If Not rs.EOF Then
    Response.Write "Found: " & rs.Fields("name").Value
Else
    Response.Write "No match"
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```