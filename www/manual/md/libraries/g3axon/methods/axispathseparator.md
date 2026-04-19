# Check If a Character Is a Path Separator

## Overview

Returns `True` when the provided single character is a valid path separator for the current platform.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxIsPathSeparator(character)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| character | String | Yes | A single character to test. Multi-character strings or empty strings always return `False`. |

## Return Value

- **Boolean**: Returns `True` when `character` is a valid path separator on the current operating system.
- **Boolean**: Returns `False` when `character` is not a path separator, is empty, is multi-character, or no argument is provided.

## Remarks

- On Windows, both `\` and `/` may be valid path separators.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write CStr(ax.AxIsPathSeparator("/")) & "<br>" ' True on Unix, possibly True on Windows
Response.Write CStr(ax.AxIsPathSeparator("a")) & "<br>" ' False

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIsPathSeparator`
- **Arguments**: `character As String`
- **Returns**: `Boolean` (`True` if the character is a valid path separator)