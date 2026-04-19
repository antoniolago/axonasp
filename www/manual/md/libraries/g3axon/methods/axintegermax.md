# Get the Maximum Platform Integer Value

## Overview

Returns the maximum value that a signed 64-bit integer can hold on the current platform.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxIntegerMax()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Returns `9,223,372,036,854,775,807` on 64-bit systems.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxIntegerMax()
' Output: 9223372036854775807

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIntegerMax`
- **Arguments**: none
- **Returns**: `Integer` (maximum signed 64-bit integer value)
