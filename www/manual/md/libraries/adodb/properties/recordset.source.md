# Recordset.Source Property

Gets or sets the source used to populate the recordset.

## Syntax

```asp
value = rs.Source
rs.Source = "SELECT id, name FROM users"
```

## Return Value

Variant. Returns the source expression, typically SQL text or command reference.

## Remarks

- Property names are case-insensitive.
- Set Source before opening the recordset.
- Source can be SQL text, table name, or a command object depending on runtime path.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.Source = "SELECT id, name FROM users"
Response.Write CStr(rs.Source)

Set rs = Nothing
%>
```