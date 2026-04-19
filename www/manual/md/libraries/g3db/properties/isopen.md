# IsOpen Property

## Overview
Reports whether the database connection pool is currently open.

## Prerequisites
```asp
Set db = Server.CreateObject("G3DB")
```

## Syntax
```asp
status = db.IsOpen
```

## Return Value
Returns a **Boolean**:
- **True** when connection is open.
- **False** when connection is closed or not initialized.

## Remarks
- This property is read-only.

## Example
```asp
<%
Dim db
Set db = Server.CreateObject("G3DB")

Response.Write db.IsOpen

Set db = Nothing
%>
```

## API Reference
- **Type:** Boolean
- **Access:** Read-only
