# Parameters.Item Property

Returns a parameter object from the command Parameters collection.

## Syntax

```asp
Set param = cmd.Parameters.Item(indexOrName)
```

## Return Value

Object or Empty. Returns ADODB.Parameter for valid lookups; can return Empty for unresolved access in compatibility paths.

## Remarks

- Property names are case-insensitive.
- Validate `Parameters.Count` before indexed reads.
- Name resolution depends on how parameters were created.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, p, p2

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
Set p = cmd.CreateParameter("id", 3, 1, 4, 1)
cmd.Parameters.Append p

Set p2 = cmd.Parameters.Item(0)
Response.Write CStr(p2.Value)

conn.Close
Set p2 = Nothing
Set p = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```