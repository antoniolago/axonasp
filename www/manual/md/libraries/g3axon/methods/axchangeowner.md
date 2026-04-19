# Change File Owner and Group

## Overview

Changes the owner and group of a file by specifying numeric user ID (uid) and group ID (gid).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxChangeOwner(path, uid, gid)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| path | String | Yes | The file path to change ownership of. |
| uid | Integer | Yes | The numeric user ID of the new owner. |
| gid | Integer | Yes | The numeric group ID of the new owner group. |

## Return Value

- **Boolean**: Returns `True` when ownership was changed successfully.
- **Boolean**: Returns `False` when fewer than three arguments are provided, the path is empty, or the operation fails due to permissions.

## Remarks

- On Windows and non-privileged Unix environments, this method commonly returns `False`.
- Typically requires root/administrator privileges on Unix-like systems.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' Change owner to root:root (uid=0, gid=0)
If ax.AxChangeOwner("/var/data/file.txt", 0, 0) Then
    Response.Write "Owner changed."
Else
    Response.Write "Failed (insufficient privileges)."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxChangeOwner`
- **Arguments**: `path As String, uid As Integer, gid As Integer`
- **Returns**: `Boolean` (`True` on success, `False` on failure)