# Execute a Shell Command

## Overview

Executes an external shell command and returns the combined stdout and stderr output as a string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxExecute(command)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| command | String | Yes | The full command line to execute. |

## Return Value

- **String**: Returns the combined stdout and stderr output of the command, with trailing newlines stripped.
- **Boolean**: Returns `False` when `command` is empty or no argument is provided.

## Remarks

- On Windows, the command runs via `cmd.exe /c`. On Unix-like systems, it runs via `sh -c`.
- This is a blocking call. The script waits until the command completes.
- Never pass user-provided input directly to this function without validation.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, output
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

output = ax.AxExecute("dir C:\\") ' Windows
Response.Write "<pre>" & Server.HTMLEncode(output) & "</pre>"

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxExecute`
- **Arguments**: `command As String`
- **Returns**: `String` (command output), or `Boolean` `False` when command is empty
