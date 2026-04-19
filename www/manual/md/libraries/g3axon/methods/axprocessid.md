# Get the Current Process ID

## Overview

Returns the operating system Process ID (PID) of the current AxonASP process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxProcessId()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Returns the numeric PID assigned by the OS to the current process.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "PID: " & ax.AxProcessId()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxProcessId`
- **Arguments**: none
- **Returns**: `Integer` (operating system process identifier)
