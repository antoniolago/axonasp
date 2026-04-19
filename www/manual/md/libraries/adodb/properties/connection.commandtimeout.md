# Connection.CommandTimeout Property

Gets or sets the default timeout for commands executed through the connection.

## Syntax

```asp
seconds = conn.CommandTimeout
conn.CommandTimeout = 30
```

## Return Value

Integer. Returns the command timeout in seconds.

## Remarks

- Property names are case-insensitive.
- Applies to commands executed via `Connection.Execute`.
- Set this property before running long or uncertain queries.
- Individual `Command.CommandTimeout` values can override this default.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
conn.CommandTimeout = 20

Response.Write "Command timeout: " & CStr(conn.CommandTimeout) & " seconds"

conn.Close
Set conn = Nothing
%>
```