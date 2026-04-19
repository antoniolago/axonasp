# Recordset.CursorType Property

Gets or sets the cursor type used by the recordset.

## Syntax

```asp
value = rs.CursorType
rs.CursorType = newValue
```

## Return Value

Integer. Returns cursor type flag.

## Remarks

- Property names are case-insensitive.
- Set this value before opening the recordset.
- Cursor type affects movement and feature availability.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.CursorType = 3
Response.Write CStr(rs.CursorType)

Set rs = Nothing
%>
```