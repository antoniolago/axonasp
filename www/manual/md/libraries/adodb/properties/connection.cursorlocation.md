# Connection.CursorLocation Property

Gets or sets the cursor location mode used by the connection.

## Syntax

```asp
mode = conn.CursorLocation
conn.CursorLocation = 3
```

## Return Value

Integer. Returns the configured cursor location flag.

## Remarks

- Property names are case-insensitive.
- Common values are `1` (server cursor) and `3` (client cursor).
- Set this property before opening recordsets that inherit connection defaults.
- Individual recordsets can override cursor location.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.CursorLocation = 3
Response.Write "CursorLocation: " & CStr(conn.CursorLocation)

Set conn = Nothing
%>
```