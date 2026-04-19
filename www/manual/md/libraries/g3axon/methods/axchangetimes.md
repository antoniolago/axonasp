# Change File Timestamps

## Overview

Changes the access and modification timestamps of a file using Unix epoch seconds.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxChangeTimes(path, accessTime, modifyTime)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| path | String | Yes | The file path whose timestamps will be updated. |
| accessTime | Integer | Yes | The new access time as a Unix epoch timestamp (seconds since 1970-01-01 UTC). |
| modifyTime | Integer | Yes | The new modification time as a Unix epoch timestamp. |

## Return Value

- **Boolean**: Returns `True` when the timestamps were changed successfully.
- **Boolean**: Returns `False` when the path is empty, the file does not exist, or the operation fails due to permissions.

## Remarks

- Requires at least three arguments; returns `False` with fewer.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, ok
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

ok = ax.AxChangeTimes("C:\\temp\\file.txt", 1700000000, 1700000001)
If ok Then
    Response.Write "Timestamps updated."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxChangeTimes`
- **Arguments**: `path As String, accessTime As Integer, modifyTime As Integer`
- **Returns**: `Boolean` (`True` on success, `False` on failure)