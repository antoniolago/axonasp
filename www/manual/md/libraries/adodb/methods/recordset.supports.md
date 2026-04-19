# Recordset.Supports Method

Checks whether a recordset feature flag is supported.

## Syntax

```asp
ok = rs.Supports(feature)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `feature` | Integer | Yes | Feature capability constant to test. |

## Return Value

Boolean. Returns True when the feature is supported; otherwise False.

## Remarks

- Method names are case-insensitive.
- Use this before calling optional operations like bookmarks or batch updates.
- Supported features vary by provider and cursor configuration.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, ok

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

ok = rs.Supports(16)
Response.Write "Supports flag 16: " & CStr(ok)

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```