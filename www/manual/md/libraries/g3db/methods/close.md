# Close a Database Connection

## Overview

Closes the current database pool managed by the G3DB object.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
ok = db.Close()
```

## Parameters

None.

## Return Value

- **Boolean `True`**: Connection closed successfully, or no connection was open.
- **Boolean `False`**: Close operation returned an error.

## Remarks

- On successful close, `IsOpen` becomes `False`.

## Example

```asp
<%
Option Explicit
Dim db, ok
Set db = Server.CreateObject("G3DB")

db.Open "sqlite", "data.db"
ok = db.Close()
Response.Write ok

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Close`
- **Arguments**: none
- **Returns**: Boolean — `True` on success, `False` on close error
