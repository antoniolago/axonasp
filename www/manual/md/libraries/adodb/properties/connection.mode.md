# Connection.Mode Property

Gets or sets the access mode for the connection.

## Syntax

```asp
mode = conn.Mode
conn.Mode = 3
```

## Return Value

Integer. Returns the current mode flag.

## Remarks

- Property names are case-insensitive.
- Typical flags include read-only and read-write combinations.
- Set Mode before calling Open.
- Unsupported mode flags can be ignored or rejected by provider.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.Mode = 3
Response.Write "Mode: " & CStr(conn.Mode)

Set conn = Nothing
%>
```