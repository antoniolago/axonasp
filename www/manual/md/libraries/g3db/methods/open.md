# Open a Database Connection

## Overview

Opens a database connection pool and validates connectivity with an internal ping.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
ok = db.Open(driver, dsn)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **driver** | String | Yes | Database driver name. |
| **dsn** | String | Yes | Driver-specific connection string. |

## Return Value

- **Boolean `True`**: Connection opened and ping validation succeeded.
- **Boolean `False`**: Arguments are missing, driver is unsupported, connection is already open, or open/ping failed.

## Remarks

- Driver names are normalized before opening.
- On failure, error details are available in `LastError`.

## Example

```asp
<%
Option Explicit
Dim db, ok
Set db = Server.CreateObject("G3DB")

ok = db.Open("mysql", "user:pass@tcp(127.0.0.1:3306)/app")
If ok Then
    db.Close
Else
    Response.Write db.LastError
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Open`
- **Arguments**: `driver` (String, required), `dsn` (String, required)
- **Returns**: Boolean — `True` on success, `False` on failure
