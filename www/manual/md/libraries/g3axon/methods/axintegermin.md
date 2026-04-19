# Get the Minimum Platform Integer Value

## Overview

Returns the minimum value that a signed 64-bit integer can hold on the current platform.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxIntegerMin()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Returns `-9,223,372,036,854,775,808` on 64-bit systems.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxIntegerMin()
' Output: -9223372036854775808

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIntegerMin`
- **Arguments**: none
- **Returns**: `Integer` (minimum signed 64-bit integer value)
