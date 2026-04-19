# Recordset.PageSize Property

Gets or sets the number of rows per logical page.

## Syntax

```asp
value = rs.PageSize
rs.PageSize = newValue
```

## Return Value

Integer. Returns configured page size.

## Remarks

- Property names are case-insensitive.
- Set this value before page-based navigation.
- A value less than 1 is invalid for page calculations.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.PageSize = 25
Response.Write CStr(rs.PageSize)

Set rs = Nothing
%>
```