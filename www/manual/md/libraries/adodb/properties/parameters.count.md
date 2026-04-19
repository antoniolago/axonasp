# Parameters.Count Property

Returns the number of parameters in the command Parameters collection.

## Syntax

```asp
count = cmd.Parameters.Count
```

## Return Value

Integer. Returns total appended parameter entries.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Count reflects only parameters added to the current command object.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, p

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
Set p = cmd.CreateParameter("id", 3, 1, 4, 1)
cmd.Parameters.Append p

Response.Write CStr(cmd.Parameters.Count)

conn.Close
Set p = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```