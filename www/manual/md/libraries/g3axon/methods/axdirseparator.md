# Get the Directory Separator Character

## Overview

Returns the character the operating system uses to separate directory components in a file path.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxDirSeparator()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns `"\"` on Windows systems.
- **String**: Returns `"/"` on Unix-like systems.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, sep
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

sep = ax.AxDirSeparator()
Response.Write "docs" & sep & "manual" & sep & "index.html"

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxDirSeparator`
- **Arguments**: none
- **Returns**: `String` (`\` on Windows, `/` on Unix)
