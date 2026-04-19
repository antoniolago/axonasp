# Get the Cache Directory Path

## Overview

Returns the absolute path to the AxonASP cache directory (`.temp/cache/`), including a trailing path separator.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxCacheDirPath()
```

## Parameters

This method does not require parameters.

## Return Value

- **String**: Returns the absolute path to the cache directory, always ending with a path separator character.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, cachePath
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

cachePath = ax.AxCacheDirPath()
Response.Write "Cache: " & cachePath
' Example output on Windows: C:\axonasp\.temp\cache\

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCacheDirPath`
- **Arguments**: none
- **Returns**: `String` (absolute path to `.temp/cache/` with trailing separator)