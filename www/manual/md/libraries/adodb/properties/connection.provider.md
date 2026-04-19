# Connection.Provider Property

Gets or sets the provider name used by the connection.

## Syntax

```asp
name = conn.Provider
conn.Provider = "MSDASQL"
```

## Return Value

String. Returns the provider identifier.

## Remarks

- Property names are case-insensitive.
- Provider can be set directly or inferred from ConnectionString.
- When both are set, provider resolution depends on the active driver/provider rules.
- Use a provider supported by your host environment.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.Provider = "MSDASQL"
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")

Response.Write "Provider: " & conn.Provider

Set conn = Nothing
%>
```