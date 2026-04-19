# Return the Minimum Value

## Overview

Returns the smallest numeric value from all provided arguments.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxMin(n1, n2, ...)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| n1, n2, ... | Double | Yes (at least one) | One or more numeric values to compare. All values are coerced to Double before comparison. |

## Return Value

- **Double**: Returns the smallest value among all arguments.
- **Integer**: Returns `0` when no arguments are provided.

## Remarks

- All values are coerced to Double before comparison.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxMin(10, 45, 32, -5.2)
' Output: -5.2

Response.Write ax.AxMin(100, 200, 150)
' Output: 100

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxMin`
- **Arguments**: `n1 As Double, n2 As Double, ...` (variadic)
- **Returns**: `Double` (smallest value among arguments)
