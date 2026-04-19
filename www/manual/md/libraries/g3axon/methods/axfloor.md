# Round a Number Down

## Overview

Returns the largest integer value less than or equal to the specified number (floor).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxFloor(number)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| number | Double | Yes | The numeric value to round down. Coerced to Double before processing. |

## Return Value

- **Double**: Returns the largest integer value that is less than or equal to `number`.
- **Integer**: Returns `0` when no argument is provided.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxFloor(4.9)  ' Output: 4
Response.Write ax.AxFloor(4.1)  ' Output: 4
Response.Write ax.AxFloor(-4.1) ' Output: -5

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxFloor`
- **Arguments**: `number As Double`
- **Returns**: `Double` (floor of input)
