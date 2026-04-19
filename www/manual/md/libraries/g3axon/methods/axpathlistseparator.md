# Get the Path List Separator Character

## Overview

Returns the character the operating system uses to separate entries in a path list, such as the `PATH` environment variable.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxPathListSeparator()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **String**: `";"` on Windows. `":"` on Unix-like systems.

## Remarks

- Use this method to build portable path list strings without hardcoding platform-specific separator characters.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, sep, pathList
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

sep = ax.AxPathListSeparator()
pathList = "/usr/bin" & sep & "/usr/local/bin" & sep & "/opt/go/bin"

Response.Write "PATH list: " & Server.HTMLEncode(pathList)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxPathListSeparator`
- **Arguments**: None
- **Returns**: String — `";"` on Windows, `":"` on Unix
