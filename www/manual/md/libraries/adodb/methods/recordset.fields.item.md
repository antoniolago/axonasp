# Recordset.Fields.Item Method

Returns a field object from the recordset Fields collection by index or name.

## Syntax

```asp
Set fld = rs.Fields.Item(indexOrName)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `indexOrName` | Integer or String | Yes | Zero-based field index or exact field name. |

## Return Value

Field. Returns an ADODB.Field object.

## Remarks

- Method names are case-insensitive.
- Invalid name or index raises a runtime error.
- Use index in loops for better performance.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, fld

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
If Not rs.EOF Then
    Set fld = rs.Fields.Item("name")
    Response.Write fld.Value
End If

rs.Close
conn.Close
Set fld = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```