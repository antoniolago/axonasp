# Command.Parameters Property

Returns the Parameters collection bound to the command.

## Syntax

```asp
Set params = cmd.Parameters
```

## Return Value

Object. Returns an ADODB.Parameters collection object.

## Remarks

- Property names are case-insensitive.
- This property is read-only.
- Use `CreateParameter` and `Parameters.Append` to populate the collection.

## Code Example

```asp
<%
Option Explicit
Dim conn, cmd, params

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set cmd = Server.CreateObject("ADODB.Command")
Set cmd.ActiveConnection = conn
Set params = cmd.Parameters

Response.Write "Parameter count: " & CStr(params.Count)

conn.Close
Set params = Nothing
Set cmd = Nothing
Set conn = Nothing
%>
```