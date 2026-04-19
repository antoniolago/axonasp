# Reverse an Array

## Overview

Returns a new array with the elements in reverse order. The original array is not modified.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
reversed = obj.AxArrayReverse(inputArray)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| inputArray | Array | Yes | The source VBArray whose elements will be reversed. |

## Return Value

- **Array**: Returns a zero-based VBArray containing the same elements as `inputArray` in reverse order.
- **Array**: Returns an empty array when `inputArray` is not a valid array.

## Remarks

- Method names are case-insensitive in VBScript dispatch.
- The function does not modify the original array in place; it returns a new array.

## Example

```asp
<%
Option Explicit
Dim ax, colors, reversed, i
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

colors = Array("Red", "Green", "Blue")
reversed = ax.AxArrayReverse(colors)

For i = 0 To UBound(reversed)
    Response.Write reversed(i) & "<br>"
Next
' Output:
' Blue
' Green
' Red

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxArrayReverse`
- **Arguments**: `inputArray As Array`
- **Returns**: `Array` (reversed copy of the input array)
