# Open a Connection from Configuration

## Overview

Opens a database connection using AxonASP configuration and environment overrides.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
ok = db.OpenFromEnv([driver])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **driver** | String | No | Driver name. Default is `mysql`. |

## Return Value

- **Boolean `True`**: Configuration was resolved and connection opened successfully.
- **Boolean `False`**: Driver is unsupported, configuration is missing, or open failed.

## Remarks

- Uses the same connection path as `Open` after DSN resolution.

## Example

```asp
<%
Option Explicit
Dim db, ok
Set db = Server.CreateObject("G3DB")

ok = db.OpenFromEnv("postgres")
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
- **Method**: `OpenFromEnv`
- **Arguments**: `driver` (String, optional)
- **Returns**: Boolean — `True` on success, `False` on failure
