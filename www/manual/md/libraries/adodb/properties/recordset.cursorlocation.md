# Recordset.CursorLocation Property

Gets or sets cursor location mode for the recordset.

## Syntax

```asp
value = rs.CursorLocation
rs.CursorLocation = newValue
```

## Return Value

Integer. Returns cursor location flag.

## Remarks

- Property names are case-insensitive.
- Typical values are server-side and client-side cursor constants.
- Set prior to opening the recordset.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.CursorLocation = 3
Response.Write CStr(rs.CursorLocation)

Set rs = Nothing
%>
```