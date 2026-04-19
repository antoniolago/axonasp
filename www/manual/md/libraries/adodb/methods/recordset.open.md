# Recordset.Open Method

Opens a recordset using a source query and connection.

## Syntax

```asp
rs.Open source, activeConnection[, cursorType[, lockType[, options]]]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `source` | String or Command | Yes | SQL text, table name, or command object. |
| `activeConnection` | Connection | Yes | Open connection used to fetch rows. |
| `cursorType` | Integer | No | Cursor behavior flag. |
| `lockType` | Integer | No | Lock mode flag. |
| `options` | Integer | No | Provider options bitmask. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- After open, use BOF/EOF and Fields for navigation and values.
- Always close the recordset after use.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = Server.CreateObject("ADODB.Recordset")
rs.Open "SELECT id, name FROM users", conn

If Not rs.EOF Then Response.Write rs.Fields("name").Value

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```