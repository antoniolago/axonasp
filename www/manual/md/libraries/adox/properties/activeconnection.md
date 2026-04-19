# Set Catalog ActiveConnection

## Overview
Use ActiveConnection to define the connection source used by ADOX.Catalog for schema discovery.

## Syntax

```asp
Set catalog.ActiveConnection = connectionObject
catalog.ActiveConnection = connectionString
value = catalog.ActiveConnection
```

## Parameters
- Setter value (required for assignment):
	- ADODB connection object, or
	- connection string.

## Return Value
Getter returns the value currently stored in ActiveConnection:
- Object when set with an ADODB connection object.
- String when set with a connection string.
- Empty when never assigned.

Setter returns no value.

## How It Works
- Assigning ActiveConnection updates the connection source used by Tables.
- Each assignment invalidates previously cached Tables metadata.

## Remarks
- Property names are case-insensitive.
- Use Set when assigning an object value.

## Example

```asp
<%
Option Explicit

Dim conn, catalog, current
Set conn = Server.CreateObject("ADODB.Connection")
conn.Open "Data Source=./temp/sample.db;Version=3;"

Set catalog = Server.CreateObject("ADOX.Catalog")
Set catalog.ActiveConnection = conn

Set current = catalog.ActiveConnection
If IsObject(current) Then
		Response.Write "ActiveConnection is an object"
Else
		Response.Write "ActiveConnection is not an object"
End If

Set current = Nothing
Set catalog = Nothing
conn.Close
Set conn = Nothing
%>
```

