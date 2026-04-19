# Clear All Environment Variables

## Overview

Removes all environment variables from the current AxonASP process environment.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxClearEnvironment()
```

## Parameters

This method does not require parameters.

## Return Value

- **Boolean**: Always returns `True` after execution.

## Remarks

- This is a destructive, process-wide operation. All inherited and set environment variables are removed.
- Use with extreme care because system utilities and libraries may fail if they depend on specific environment variables.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' WARNING: Clears ALL environment variables from the process
ax.AxClearEnvironment()
Response.Write "Environment cleared."

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxClearEnvironment`
- **Arguments**: none
- **Returns**: `Boolean` (always `True`)
```
