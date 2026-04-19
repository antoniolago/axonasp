# Connection.ConnectionString Property

Gets or sets the full database connection string.

## Syntax

```asp
text = conn.ConnectionString
conn.ConnectionString = "Driver={SQLite3};Data Source=C:\\data\\app.db"
```

## Return Value

String. Returns the current connection string text.

## Remarks

- Property names are case-insensitive.
- Set ConnectionString before calling `Connection.Open`.
- Include provider and data source in the value.
- Invalid connection strings raise provider errors when opening the connection.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
Response.Write "Configured: " & conn.ConnectionString

conn.Open
Response.Write "<br>State: " & CStr(conn.State)

conn.Close
Set conn = Nothing
%>
```