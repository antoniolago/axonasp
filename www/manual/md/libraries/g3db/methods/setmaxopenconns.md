# Set Maximum Open Connections

## Overview

Sets the maximum number of open pooled connections for the active database handle.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
db.SetMaxOpenConns count
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **count** | Integer | Yes | Maximum number of open pooled connections. |

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
    db.SetMaxOpenConns 50
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `SetMaxOpenConns`
- **Arguments**: `count` (Integer, required)
- **Returns**: Empty
