# Connection.Version Property

Returns the ADODB compatibility version string exposed by the runtime.

## Syntax

```asp
text = conn.Version
```

## Return Value

String. Returns the version identifier for the ADODB compatibility surface.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use this value for diagnostics and compatibility reporting.
- The value does not represent the underlying database engine version.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
Response.Write "ADODB compatibility version: " & conn.Version

Set conn = Nothing
%>
```