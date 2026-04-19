# Recordset.LockType Property

Gets or sets the lock strategy used for record updates.

## Syntax

```asp
value = rs.LockType
rs.LockType = newLockType
```

## Return Value

Integer. Returns lock mode flag.

## Remarks

- Property names are case-insensitive.
- Set before opening the recordset.
- Lock strategy affects concurrency and update behavior.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.LockType = 3
Response.Write CStr(rs.LockType)

Set rs = Nothing
%>
```