# Fields.Append Method

Appends a new field definition to a Fields collection.

## Syntax

```asp
fields.Append name[, type[, definedSize[, attributes]]]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | String | Yes | Field name to append. |
| `type` | Integer | No | ADODB data type code. |
| `definedSize` | Integer | No | Declared size for variable-length fields. |
| `attributes` | Integer | No | Field attribute bitmask. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Append is used for dynamic schema creation scenarios.
- Provider support for runtime schema mutation can vary.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.Fields.Append "TempName", 200, 100

Response.Write "Field appended"

Set rs = Nothing
%>
```