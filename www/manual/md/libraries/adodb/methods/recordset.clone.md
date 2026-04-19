# Recordset.Clone Method

Creates a new Recordset object that references the same rowset data.

## Syntax

```asp
Set rsClone = rs.Clone
```

## Parameters

No parameters.

## Return Value

Recordset. Returns a new ADODB.Recordset object clone.

## Remarks

- Method names are case-insensitive.
- The clone has independent cursor position.
- Changes to shared underlying data can be visible in both recordsets, depending on lock and cursor behavior.
- Close and release cloned recordsets separately.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, rsClone

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
Set rsClone = rs.Clone

If Not rs.EOF Then
    Response.Write "Original current row: " & rs.Fields("name").Value & "<br>"
End If

If Not rsClone.EOF Then
    Response.Write "Clone current row: " & rsClone.Fields("name").Value
End If

rsClone.Close
rs.Close
conn.Close
Set rsClone = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```