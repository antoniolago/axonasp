# Count Elements in an Array

## Overview

Returns the total number of elements in a zero-based VBArray.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxCount(array)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| array | Array | Yes | The VBArray to measure. |

## Return Value

- **Integer**: Returns the number of elements in `array`.
- **Integer**: Returns `0` when the input is not a valid array or no argument is provided.

## Remarks

- Equivalent to `UBound(arr) - LBound(arr) + 1` for single-dimensional arrays.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, items
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

items = Array("A", "B", "C", "D")
Response.Write ax.AxCount(items)
' Output: 4

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCount`
- **Arguments**: `array As Array`
- **Returns**: `Integer` (number of elements)
