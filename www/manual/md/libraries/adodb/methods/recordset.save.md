# Recordset.Save Method

Saves recordset content to a file path or stream target.

## Syntax

```asp
rs.Save destination
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `destination` | String or Object | Yes | Output file path or stream object target. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- Output format depends on runtime implementation and destination handling.
- Ensure destination path is writable.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, path

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

path = Server.MapPath("./users.xml")
rs.Save path
Response.Write "Saved to: " & path

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```