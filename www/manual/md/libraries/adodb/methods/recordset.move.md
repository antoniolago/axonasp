# Recordset.Move Method

Moves the current cursor position by a relative row offset.

## Syntax

```asp
rs.Move offset
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offset` | Integer | Yes | Positive to move forward, negative to move backward. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Cursor movement beyond bounds sets BOF or EOF accordingly.
- Move supports flexible navigation without repeated MoveNext or MovePrevious calls.
- Use with cursor types that support requested direction.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
rs.MoveFirst
rs.Move 2

If Not rs.EOF Then
    Response.Write "Current row after Move 2: " & rs.Fields("name").Value
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```