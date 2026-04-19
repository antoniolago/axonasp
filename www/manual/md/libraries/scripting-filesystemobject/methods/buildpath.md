# BuildPath Method

## Overview

Concatenates a base path and a file or folder name using the OS path separator and returns the resulting path string.

## Syntax

```asp
result = fso.BuildPath(path, name)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| path | String | Yes | The base path to which name is appended. |
| name | String | Yes | The file or folder name to append to path. |

## Return Value

Returns a **String** containing the concatenated path. The method uses the OS path separator (`\` on Windows, `/` on Unix). If fewer than two arguments are supplied, returns an empty String.

## How It Works

The method calls the Go `filepath.Join` function on the two arguments. No path validation or resolution is performed; the inputs are joined as-is. The result is not checked for existence on disk.

## Remarks

- `BuildPath` does not create any directory or file on disk.
- The method does not resolve relative paths or validate the result against the web root.
- Use `Server.MapPath` when you need an absolute server path, then pass the result to `BuildPath` if you need to append a sub-path.

## Code Example

```asp
<%
Option Explicit
Dim fso, fullPath
Set fso = Server.CreateObject("Scripting.FileSystemObject")

fullPath = fso.BuildPath("C:\\data", "report.txt")
Response.Write fullPath
' Output: C:\data\report.txt

Set fso = Nothing
%>
```

