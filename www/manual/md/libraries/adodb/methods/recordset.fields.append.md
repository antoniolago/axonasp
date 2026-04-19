# Recordset.Fields.Append Method

Appends a field definition to the current Recordset Fields collection.

## Syntax

```asp
rs.Fields.Append name[, type[, definedSize[, attributes]]]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | Field name to add. |
| `type` | Integer | No | ADODB type code for the new field. |
| `definedSize` | Integer | No | Maximum size for variable-length field types. |
| `attributes` | Integer | No | Field attribute flags. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Use before opening or materializing data when building dynamic structures.
- Field schema changes are provider/runtime dependent.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.Fields.Append "Code", 200, 20
rs.Fields.Append "Description", 200, 255

Response.Write "Fields appended: " & CStr(rs.Fields.Count)

Set rs = Nothing
%>
```