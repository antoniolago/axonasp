# Driver Property

## Overview
Gets or sets the normalized database driver name.

## Prerequisites
```asp
Set db = Server.CreateObject("G3DB")
```

## Syntax
```asp
db.Driver = "mysql"
driverName = db.Driver
```

## Return Value
Returns a **String** with the current normalized driver value.

## Remarks
- This property is read/write.
- Assigned values are normalized to canonical driver names.

## Example
```asp
<%
Dim db
Set db = Server.CreateObject("G3DB")

db.Driver = "postgresql"
Response.Write db.Driver

Set db = Nothing
%>
```

## API Reference
- **Type:** String
- **Access:** Read/write
