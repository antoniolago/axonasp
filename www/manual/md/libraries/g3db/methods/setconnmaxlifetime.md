# Set Maximum Connection Lifetime

## Overview

Sets the maximum reuse lifetime for pooled connections on the active database handle.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
db.SetConnMaxLifetime seconds
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **seconds** | Integer | Yes | Maximum connection lifetime in seconds. |

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
    db.SetConnMaxLifetime 3600
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `SetConnMaxLifetime`
- **Arguments**: `seconds` (Integer, required)
- **Returns**: Empty
