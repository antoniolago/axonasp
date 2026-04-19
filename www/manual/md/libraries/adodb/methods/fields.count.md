# Fields.Count Method

Returns the number of columns in the Fields collection.

## Syntax

```asp
count = rs.Fields.Count
```

## Parameters

No parameters.

## Return Value

Integer. Returns the number of Field objects in the current Recordset schema.

## Remarks

- Method names are case-insensitive.
- Count reflects the selected columns in the current query.
- The value is available after the Recordset is opened.
- Use Count to iterate safely over the fields collection.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, i

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name, email FROM users")
Response.Write "Field count: " & CStr(rs.Fields.Count) & "<br>"

For i = 0 To rs.Fields.Count - 1
    Response.Write "Column " & CStr(i) & ": " & rs.Fields.Item(i).Name & "<br>"
Next

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```