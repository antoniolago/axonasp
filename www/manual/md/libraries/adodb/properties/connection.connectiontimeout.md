# Connection.ConnectionTimeout Property

Gets or sets the timeout for establishing the connection, in seconds.

## Syntax

```asp
seconds = conn.ConnectionTimeout
conn.ConnectionTimeout = 15
```

## Return Value

Integer. Returns the configured connection timeout in seconds.

## Remarks

- Property names are case-insensitive.
- Set this property before calling `Connection.Open`.
- Lower values fail faster on unavailable endpoints.
- Very low values can cause failures on slow networks or startup-heavy providers.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.ConnectionTimeout = 10

Response.Write "Connection timeout: " & CStr(conn.ConnectionTimeout) & " seconds"

conn.Open
conn.Close
Set conn = Nothing
%>
```