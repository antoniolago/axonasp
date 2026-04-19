# Get the Platform Architecture Bit Width

## Overview

Returns the native integer bit size of the current platform (typically 32 or 64).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxPlatformBits()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Returns `32` on 32-bit systems and `64` on 64-bit systems.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxPlatformBits() & "-bit"
' Output: 64-bit

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxPlatformBits`
- **Arguments**: none
- **Returns**: `Integer` (32 or 64)
