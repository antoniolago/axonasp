# DSN Property

## Overview
Gets or sets the connection string value stored in the G3DB object.

## Prerequisites
```asp
Set db = Server.CreateObject("G3DB")
```

## Syntax
```asp
db.DSN = "user:pass@tcp(localhost:3306)/app"
currentDsn = db.DSN
```

## Return Value
Returns a **String** with the current DSN value.

## Remarks
- This property is read/write.
- `Open(driver, dsn)` also updates this property when open succeeds.

## Example
```asp
<%
Dim db
Set db = Server.CreateObject("G3DB")

db.DSN = "data.db"
Response.Write db.DSN

Set db = Nothing
%>
```

## API Reference
- **Type:** String
- **Access:** Read/write
