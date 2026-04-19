# CopyFolder Method

## Overview

Recursively copies a folder and all of its contents to a destination path.

## Syntax

```asp
fso.CopyFolder source, destination [, overwrite]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| source | String | Yes | The full path to the folder to copy. |
| destination | String | Yes | The full destination path for the copied folder. |
| overwrite | Boolean | No | Set to True (default) to overwrite existing files in the destination. Set to False to skip existing files. |

## Return Value

Returns **Empty**. The method does not return a value.

## How It Works

Both `source` and `destination` are resolved against the web root. The runtime creates any missing parent directories in the destination path before copying files. All files and sub-folders within `source` are copied recursively. If `overwrite` is False, individual files that already exist at the destination are not replaced.

## Remarks

- The `overwrite` parameter defaults to `True`.
- If either path cannot be resolved, the operation is silently skipped.
- Use `On Error Resume Next` to guard against permission or path errors at runtime.

## Code Example

```asp
<%
Option Explicit
Dim fso
Set fso = Server.CreateObject("Scripting.FileSystemObject")

On Error Resume Next
fso.CopyFolder Server.MapPath("templates"), Server.MapPath("backup/templates"), True
If Err.Number <> 0 Then
    Response.Write "CopyFolder failed: " & Err.Description
End If
On Error GoTo 0

Set fso = Nothing
%>
```

