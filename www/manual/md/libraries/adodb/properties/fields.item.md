# Fields.Item Property

Returns a field object from the Fields collection by index or name.

## Syntax

```asp
Set fld = rs.Fields.Item(indexOrName)
```

## Return Value

Object. Returns an ADODB.Field object.

## Remarks

- Property names are case-insensitive.
- Invalid references raise runtime errors.
- Prefer names for readability and indexes for loops.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, fld

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open
Set rs = conn.Execute("SELECT id, name FROM users")

Set fld = rs.Fields.Item("name")
Response.Write fld.Value

rs.Close
conn.Close
Set fld = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```