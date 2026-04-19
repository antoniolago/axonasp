# Recordset.Fields Property

Returns the Fields collection for the current recordset schema.

## Syntax

```asp
Set fieldsCollection = rs.Fields
```

## Return Value

Object. Returns an ADODB.Fields collection.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use `Fields.Count` and `Fields.Item` to inspect columns.

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
Response.Write CStr(fieldsCollection.Count)

rs.Close
conn.Close
Set fieldsCollection = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```