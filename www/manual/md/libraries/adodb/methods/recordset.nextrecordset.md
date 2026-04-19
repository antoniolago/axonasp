# Recordset.NextRecordset Method

Returns the next recordset when a command produces multiple result sets.

## Syntax

```asp
Set nextRs = rs.NextRecordset
```

## Parameters

No parameters.

## Return Value

Recordset or Nothing. Returns the next ADODB.Recordset object if available; returns Nothing when there are no additional result sets.

## Remarks

- Method names are case-insensitive.
- Use NextRecordset only when SQL/provider can emit multiple result sets.
- Always check if returned object is Nothing before using it.
- Close each returned recordset when finished.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, nextRs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id FROM users")
Set nextRs = rs.NextRecordset

If IsObject(nextRs) Then
    Response.Write "Second recordset available"
    nextRs.Close
Else
    Response.Write "No additional recordset"
End If

rs.Close
conn.Close
Set nextRs = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```