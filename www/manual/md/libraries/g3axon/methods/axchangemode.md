# Change File Mode Permissions

## Overview

Changes the mode (permission bits) of a file using an octal string (for example, `"0644"`).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxChangeMode(path, mode)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| path | String | Yes | The file path to modify. |
| mode | String | Yes | The octal permission string (for example, `"0644"`, `"0755"`). |

## Return Value

- **Boolean**: Returns `True` when the mode was applied successfully.
- **Boolean**: Returns `False` when fewer than two arguments are provided, the path or mode is empty, the octal string is invalid, or the operation fails due to permissions.

## Remarks

- This method applies the Unix-style file mode bits. On Windows, the effect is limited; only the read-only attribute is affected.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

If ax.AxChangeMode("/var/www/upload.log", "0644") Then
    Response.Write "Permissions updated."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxChangeMode`
- **Arguments**: `path As String, mode As String`
- **Returns**: `Boolean` (`True` on success, `False` on failure)