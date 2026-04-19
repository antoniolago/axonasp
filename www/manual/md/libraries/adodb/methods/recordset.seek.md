# Recordset.Seek Method

Repositions the cursor using an index key.

## Syntax

```asp
rs.Seek keyOrPosition
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `keyOrPosition` | Variant | Yes | Key or position value used by the provider seek implementation. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Seek support depends on provider and recordset index configuration.
- Set `Recordset.Index` before calling Seek when required.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

rs.Index = "id"
rs.Seek 1
If Not rs.EOF Then Response.Write rs.Fields("name").Value

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```