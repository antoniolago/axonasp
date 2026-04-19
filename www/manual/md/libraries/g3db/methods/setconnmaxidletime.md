# Set Maximum Connection Idle Time

## Overview

Sets the idle timeout for pooled connections on the active database handle.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
db.SetConnMaxIdleTime seconds
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **seconds** | Integer | Yes | Maximum idle time in seconds. |

## Return Value

- **Empty**: Always returned.

## Remarks

- Setting is applied only when a connection is open.

## Example

```asp
<%
Option Explicit
Dim db
Set db = Server.CreateObject("G3DB")

If db.Open("mysql", "user:pass@tcp(localhost)/db") Then
    db.SetConnMaxIdleTime 120
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `SetConnMaxIdleTime`
- **Arguments**: `seconds` (Integer, required)
- **Returns**: Empty
