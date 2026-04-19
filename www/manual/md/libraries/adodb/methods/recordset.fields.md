# Recordset.Fields Method

Returns the Fields collection associated with the current recordset.

## Syntax

```asp
Set fieldsCollection = rs.Fields
```

## Parameters

No parameters.

## Return Value

Object. Returns an ADODB.Fields collection object.

## Remarks

- Method names are case-insensitive.
- Use the collection to inspect schema and read field values.
- Combine with `Fields.Count` and `Fields.Item` for dynamic processing.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, fieldsCollection

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
Set fieldsCollection = rs.Fields

Response.Write "Fields: " & CStr(fieldsCollection.Count)

rs.Close
conn.Close
Set fieldsCollection = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```