# Create a Numeric Range Array

## Overview

Builds and returns a zero-based VBArray containing Integer values from `start` to `end`, progressing by `step`.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
arr = obj.AxRange(start, end [, step])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| start | Integer | Yes | The first value in the range. |
| end | Integer | Yes | The last value in the range (inclusive). |
| step | Integer | Optional | The increment between values. Defaults to `1`. A negative step generates a descending range. |

## Return Value

- **Array**: Returns a zero-based VBArray of Integer values from `start` to `end`.
- **Array**: Returns an empty array when fewer than two arguments are provided.

## Remarks

- When `step` is `0`, it defaults to `1`.
- For a descending range, provide a negative `step` and set `start` greater than `end`.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, nums, i
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' Ascending range 1 to 5
nums = ax.AxRange(1, 5)
For i = 0 To UBound(nums)
    Response.Write nums(i) & " "
Next
' Output: 1 2 3 4 5

' Step of 2
nums = ax.AxRange(0, 10, 2)
For i = 0 To UBound(nums)
    Response.Write nums(i) & " "
Next
' Output: 0 2 4 6 8 10

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxRange`
- **Arguments**: `start As Integer, end As Integer [, step As Integer]`
- **Returns**: `Array` (zero-based VBArray of Integer values)
