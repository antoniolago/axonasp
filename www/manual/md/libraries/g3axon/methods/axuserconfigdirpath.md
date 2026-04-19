# Get the Configuration File Path

## Overview

Returns the resolved absolute path to the AxonASP configuration file (`config/axonasp.toml`).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxUserConfigDirPath()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the absolute path to `config/axonasp.toml`, resolved from common search locations relative to the executable.

## Remarks

- The path is resolved by searching `./config/axonasp.toml`, `../config/axonasp.toml`, and the directory of the running executable.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "Config path: " & ax.AxUserConfigDirPath()

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxUserConfigDirPath`
- **Arguments**: none
- **Returns**: `String` (absolute path to `config/axonasp.toml`)