# Get the Float Precision Digit Count

## Overview

Returns the standard number of significant decimal digits for IEEE-754 double-precision floating-point values.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxFloatPrecisionDigits()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Always returns `15`.

## Remarks

- This is a constant reflecting IEEE-754 double-precision capability.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxFloatPrecisionDigits()
' Output: 15

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxFloatPrecisionDigits`
- **Arguments**: none
- **Returns**: `Integer` (always `15`)
