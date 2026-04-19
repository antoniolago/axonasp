# Change the Current Working Directory

## Overview

Changes the current working directory of the AxonASP process to the specified path.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxChangeDir(path)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| path | String | Yes | The absolute or relative path of the directory to switch to. |

## Return Value

- **Boolean**: Returns `True` when the directory was changed successfully.
- **Boolean**: Returns `False` when the path is invalid, inaccessible, or no argument is provided.

## Remarks

- Changing the working directory affects the entire process. In a multi-threaded web server environment, use this function with caution because it may interfere with other concurrent requests.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, ok
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

ok = ax.AxChangeDir("C:\Windows\Temp")
If ok Then
    Response.Write "Directory changed to: " & ax.AxCurrentDir()
Else
    Response.Write "Failed to change directory."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxChangeDir`
- **Arguments**: `path As String`
- **Returns**: `Boolean` (`True` on success, `False` on failure)
%>
```
