# Create a Hard Link

## Overview

Creates a hard link at `linkPath` that points to the existing file at `sourcePath`.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxCreateLink(sourcePath, linkPath)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| sourcePath | String | Yes | The path of the existing file to link to. |
| linkPath | String | Yes | The path of the new hard link to create. |

## Return Value

- **Boolean**: Returns `True` when the hard link was created successfully.
- **Boolean**: Returns `False` when fewer than two arguments are provided, either path is empty, or the operation fails.

## Remarks

- Hard links share the same inode as the source; deleting one does not remove the other.
- Some restricted environments or file system types may deny link creation.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

If ax.AxCreateLink("/var/data/original.txt", "/var/data/backup.txt") Then
    Response.Write "Hard link created."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCreateLink`
- **Arguments**: `sourcePath As String, linkPath As String`
- **Returns**: `Boolean` (`True` on success, `False` on failure)