# Connection.IsolationLevel Property

Gets or sets the transaction isolation level used for new transactions.

## Syntax

```asp
level = conn.IsolationLevel
conn.IsolationLevel = 4096
```

## Return Value

Integer. Returns the configured isolation level flag.

## Remarks

- Property names are case-insensitive.
- Isolation level affects locking and visibility rules during transactions.
- Set before calling BeginTrans.
- Provider support for specific isolation flags can vary.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.IsolationLevel = 4096
Response.Write "IsolationLevel: " & CStr(conn.IsolationLevel)

Set conn = Nothing
%>
```