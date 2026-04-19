# Connection.DefaultDatabase Property

Gets or sets the default database or catalog used by the connection.

## Syntax

```asp
name = conn.DefaultDatabase
conn.DefaultDatabase = "main"
```

## Return Value

String. Returns the default database name.

## Remarks

- Property names are case-insensitive.
- Use this property to control unqualified table resolution.
- Effective behavior depends on the underlying provider.
- Set before running queries that rely on default catalog context.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.DefaultDatabase = "main"
Response.Write "DefaultDatabase: " & conn.DefaultDatabase

Set conn = Nothing
%>
```