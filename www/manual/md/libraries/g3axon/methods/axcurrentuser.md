# Get the Current Process User Name

## Overview

Returns the username of the operating system user running the current AxonASP process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxCurrentUser()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the username of the process owner.
- **String**: Returns an empty string when the username cannot be determined.

## Remarks

- On Windows, falls back to the `USERNAME` environment variable if the system API call fails.
- On Unix-like systems, falls back to the `USER` environment variable if the system API call fails.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "Process user: " & ax.AxCurrentUser()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCurrentUser`
- **Arguments**: none
- **Returns**: `String` (username of the process owner, or empty string)
