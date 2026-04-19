# CopyFile Method

## Overview

Copies one file from a source path to a destination path.

## Syntax

```asp
fso.CopyFile source, destination [, overwrite]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| source | String | Yes | The full path to the file to copy. |
| destination | String | Yes | The full path or target directory for the copied file. |
| overwrite | Boolean | No | Set to True (default) to overwrite an existing destination file. Set to False to skip if the destination already exists. |

## Return Value

Returns **Empty**. The method does not return a value.

## How It Works

Both `source` and `destination` are resolved against the web root. If either path cannot be resolved, the copy operation is silently skipped. When `overwrite` is True, the destination file is replaced if it already exists. Parent directories of the destination are not created automatically.

## Remarks

- The `overwrite` parameter defaults to `True`.
- Use `On Error Resume Next` to catch permission or path errors at runtime.
- To copy an entire directory tree, use `CopyFolder` instead.

## Code Example

```asp
<%
Option Explicit
Dim fso
Set fso = Server.CreateObject("Scripting.FileSystemObject")

On Error Resume Next
fso.CopyFile Server.MapPath("source.txt"), Server.MapPath("backup/source.txt"), True
If Err.Number <> 0 Then
    Response.Write "Copy failed: " & Err.Description
End If
On Error GoTo 0

Set fso = Nothing
%>
```

