# Get the Executable Path

## Overview

Returns the absolute path of the AxonASP executable file currently running the process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxExecutablePath()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the absolute path to the running executable file.
- **String**: Returns an empty string when the path cannot be determined.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "Executable: " & ax.AxExecutablePath()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxExecutablePath`
- **Arguments**: none
- **Returns**: `String` (absolute path to the running executable)
