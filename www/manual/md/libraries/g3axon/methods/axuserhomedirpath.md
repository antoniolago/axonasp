# Get the User Home Directory Path

## Overview

Returns the absolute path of the home directory for the user running the AxonASP process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxUserHomeDirPath()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the absolute path of the current user's home directory.
- **String**: Returns an empty string when the home directory cannot be determined.

## Remarks

- On Windows, falls back to `USERPROFILE` then `HOME` environment variables.
- On Unix-like systems, falls back to the `HOME` environment variable.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "Home: " & ax.AxUserHomeDirPath()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxUserHomeDirPath`
- **Arguments**: none
- **Returns**: `String` (absolute home directory path)