# Round a Number Up

## Overview

Returns the smallest integer value greater than or equal to the specified number (ceiling).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxCeil(number)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| number | Double | Yes | The numeric value to round up. Coerced to Double before processing. |

## Return Value

- **Double**: Returns the smallest integer value that is greater than or equal to `number`.
- **Integer**: Returns `0` when no argument is provided.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxCeil(4.1)  ' Output: 5
Response.Write ax.AxCeil(4.9)  ' Output: 5
Response.Write ax.AxCeil(-4.1) ' Output: -4

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCeil`
- **Arguments**: `number As Double`
- **Returns**: `Double` (ceiling of input)
