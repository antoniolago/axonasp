# Generate a Random Integer

## Overview

Returns a pseudo-random Integer. Supports three call forms: unconstrained, single-bound, and range-bound.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxRand([max])
result = obj.AxRand(min, max)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| (none) | — | Optional | When called with no arguments, returns any non-negative random Integer. |
| max | Integer | Optional | When called with one argument, returns an Integer between `0` and `max` (inclusive). |
| min | Integer | Optional | When called with two arguments, the lower bound (inclusive). Swapped automatically if greater than `max`. |
| max | Integer | Optional | When called with two arguments, the upper bound (inclusive). |

## Return Value

- **Integer**: Returns a pseudo-random Integer within the specified range (inclusive on both ends).

## Remarks

- When `min` is greater than `max`, the bounds are automatically swapped.
- When `max` is `0` or less and only one argument is provided, returns `0`.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' Any non-negative integer
Response.Write ax.AxRand() & "<br>"

' Between 0 and 10
Response.Write ax.AxRand(10) & "<br>"

' Between 1 and 100
Response.Write ax.AxRand(1, 100) & "<br>"

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxRand`
- **Arguments**: `[max As Integer]` or `[min As Integer, max As Integer]`
- **Returns**: `Integer` (pseudo-random integer within the specified range)
