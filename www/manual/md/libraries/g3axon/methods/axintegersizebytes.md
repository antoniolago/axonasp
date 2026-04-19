# Get the Native Integer Size in Bytes

## Overview

Returns the number of bytes used to store a native integer on the current platform.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxIntegerSizeBytes()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Returns `4` on 32-bit systems and `8` on 64-bit systems.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxIntegerSizeBytes() & " bytes"
' Output: 8 bytes (on a 64-bit system)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIntegerSizeBytes`
- **Arguments**: none
- **Returns**: `Integer` (4 on 32-bit, 8 on 64-bit)
