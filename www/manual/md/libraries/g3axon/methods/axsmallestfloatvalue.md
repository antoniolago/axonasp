# Get the Smallest Positive Float Value

## Overview

Returns the smallest positive non-zero value representable by a 64-bit double-precision float.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxSmallestFloatValue()
```

## Parameters

This method does not require parameters.

## Return Value

- **Double**: Returns `5e-324` (equivalent to `math.SmallestNonzeroFloat64` in Go).

## Remarks

- Use this value for epsilon comparisons to detect near-zero floating-point differences.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, tiny
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

tiny = ax.AxSmallestFloatValue()
Response.Write "Smallest float: " & tiny

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxSmallestFloatValue`
- **Arguments**: none
- **Returns**: `Double` (5e-324)
