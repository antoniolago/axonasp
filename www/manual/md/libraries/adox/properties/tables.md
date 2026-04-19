# Get Catalog Tables

## Overview
Use Tables to retrieve the catalog table collection for the current ActiveConnection.

## Prerequisites
- Set ActiveConnection before reading Tables.

## Syntax

```asp
Set tables = catalog.Tables
count = tables.Count
Set oneTable = tables.Item(0)
```

## Parameters
- Getter only. This property accepts no arguments.

## Return Value
Returns an object reference to an ADOX tables collection.

The collection exposes:
- Count (Integer): number of discovered items.
- Item(indexOrName) (Object or Empty): returns one table object by zero-based index or case-insensitive table name.

Each table object exposes:
- Name (String)
- Type (String)

## How It Works
- On first read, the runtime resolves schema metadata from ActiveConnection and builds the collection.
- The collection is cached until ActiveConnection changes.

## Remarks
- Tables is read-only.
- Use Set when assigning object returns.

## Example

```asp
<%
Option Explicit

Dim conn, catalog, tables, firstTable
Set conn = Server.CreateObject("ADODB.Connection")
conn.Open "Data Source=./temp/sample.db;Version=3;"

Set catalog = Server.CreateObject("ADOX.Catalog")
Set catalog.ActiveConnection = conn
Set tables = catalog.Tables

Response.Write "Count=" & tables.Count & "<br>"
If tables.Count > 0 Then
	Set firstTable = tables.Item(0)
	Response.Write "First name=" & firstTable.Name & "<br>"
	Response.Write "First type=" & firstTable.Type
	Set firstTable = Nothing
End If

Set tables = Nothing
Set catalog = Nothing
conn.Close
Set conn = Nothing
%>
```

