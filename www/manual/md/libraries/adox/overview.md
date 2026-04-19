# Use ADOX.Catalog in G3Pix AxonASP

## Overview
Use ADOX.Catalog to inspect database table metadata through the catalog surface implemented by G3Pix AxonASP.

## Prerequisites
- A valid ADO connection object or connection string.
- A database provider supported by the current runtime path.

## Syntax
```asp
Set catalog = Server.CreateObject("ADOX.Catalog")
catalog.ActiveConnection = connectionObject
Set tables = catalog.Tables
```

## Parameters and Arguments
- ProgID (String, required): Use ADOX.Catalog.
- ActiveConnection assignment value (required before reading schema):
	- ADODB connection object, or
	- connection string.

## Return Value
`Server.CreateObject("ADOX.Catalog")` returns an object reference to the catalog instance.

## How It Works
- The catalog stores ActiveConnection and resolves table metadata when Tables is read.
- On Windows, the runtime first attempts OLE schema discovery.
- When OLE is not available, the runtime uses native schema queries supported by the current connection backend.

## Remarks
- Member names are case-insensitive.
- Tables is evaluated lazily and cached until ActiveConnection is changed.

## Example
```asp
<%
Option Explicit

Dim conn, catalog, tables
Set conn = Server.CreateObject("ADODB.Connection")
conn.Open "Data Source=./temp/sample.db;Version=3;"

Set catalog = Server.CreateObject("ADOX.Catalog")
Set catalog.ActiveConnection = conn
Set tables = catalog.Tables

Response.Write "Table count: " & tables.Count

Set tables = Nothing
Set catalog = Nothing
conn.Close
Set conn = Nothing
%>
```

