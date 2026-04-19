# Return the Constant Pi

## Overview

Returns the mathematical constant Pi (π = 3.141592653589793...).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxPi()
```

## Parameters

This method does not require parameters.

## Return Value

- **Double**: Returns `3.141592653589793` (the IEEE-754 double-precision representation of Pi).

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, area, radius
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

radius = 5
area = ax.AxPi() * radius * radius
Response.Write "Circle area: " & area
' Output: Circle area: 78.5398163397448

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxPi`
- **Arguments**: none
- **Returns**: `Double` (3.141592653589793)
