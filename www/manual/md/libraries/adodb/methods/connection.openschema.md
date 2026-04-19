# Connection.OpenSchema Method

Returns schema metadata as a Recordset.

## Syntax

```asp
Set rs = conn.OpenSchema(schemaId[, restrictions])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `schemaId` | Integer | No | Schema type selector. |
| `restrictions` | Variant | No | Restriction array or provider-specific filter values. |

## Return Value

Recordset. Returns an ADODB.Recordset containing schema rows for the requested schema type.

## Remarks

- Method names are case-insensitive.
- Supported schema sets depend on provider capabilities.
- Validate field availability in returned schema recordset.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.OpenSchema(20)
If Not rs.EOF Then
    Response.Write "Schema row available"
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```