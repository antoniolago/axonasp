# Set Maximum Idle Connections

## Overview

Sets the maximum number of idle pooled connections for the active database handle.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
db.SetMaxIdleConns count
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **count** | Integer | Yes | Maximum number of idle pooled connections. |

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
    db.SetMaxIdleConns 10
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `SetMaxIdleConns`
- **Arguments**: `count` (Integer, required)
- **Returns**: Empty
