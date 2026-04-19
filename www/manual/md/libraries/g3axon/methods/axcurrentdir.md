# Get the Current Working Directory

## Overview

Returns the absolute path of the current working directory of the AxonASP process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxCurrentDir()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the absolute path of the current working directory.
- **String**: Returns an empty string when an OS error occurs.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "Working directory: " & ax.AxCurrentDir()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCurrentDir`
- **Arguments**: none
- **Returns**: `String` (absolute path of the current working directory)
