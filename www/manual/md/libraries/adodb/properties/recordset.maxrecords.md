# Recordset.MaxRecords Property

Gets or sets the maximum number of rows the recordset should return.

## Syntax

```asp
value = rs.MaxRecords
rs.MaxRecords = newValue
```

## Return Value

Integer. Returns maximum rows limit.

## Remarks

- Property names are case-insensitive.
- Set this before opening the recordset.
- `0` usually means no explicit limit.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.MaxRecords = 100
Response.Write CStr(rs.MaxRecords)

Set rs = Nothing
%>
```