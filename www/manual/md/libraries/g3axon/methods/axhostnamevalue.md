# Get the Machine Hostname

## Overview

Returns the network hostname of the machine where the AxonASP process is running.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxHostnameValue()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the system hostname as reported by the operating system.
- **String**: Returns an empty string when the hostname cannot be determined.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "Hostname: " & ax.AxHostnameValue()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxHostnameValue`
- **Arguments**: none
- **Returns**: `String` (machine hostname, or empty string)
