# Recordset.GetString Method

Returns recordset rows as a single formatted string.

## Syntax

```asp
text = rs.GetString
```

## Parameters

No parameters.

## Return Value

String. Returns row data with tab-delimited columns and newline-delimited rows. Returns an empty string when no rows are available.

## Remarks

- Method names are case-insensitive.
- Output is useful for export, debug logs, or plain-text rendering.
- Large datasets may produce large memory allocations.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, text

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
text = rs.GetString

Response.Write "<pre>" & text & "</pre>"

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```