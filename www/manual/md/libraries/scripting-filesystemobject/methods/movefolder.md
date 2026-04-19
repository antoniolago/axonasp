# MoveFolder Method

## Overview

Moves a folder and all of its contents from a source path to a destination path.

## Syntax

```asp
fso.MoveFolder source, destination
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| source | String | Yes | The full path of the folder to move. |
| destination | String | Yes | The full destination path for the moved folder. |

## Return Value

Returns **Empty**. The method does not return a value.

## How It Works

Both paths are resolved against the web root. The runtime first attempts `os.Rename` for an atomic move. If the rename fails (for example, across different volumes), the runtime falls back to a recursive copy-then-delete sequence. Any existing destination at that path is replaced. Parent directories of the destination are created automatically during the fallback path.

## Remarks

- If either path cannot be resolved, the operation is silently skipped.
- To move only a single file, use `MoveFile` instead.
- Use `On Error Resume Next` to handle errors gracefully at runtime.

## Code Example

```asp
<%
Option Explicit
Dim fso
Set fso = Server.CreateObject("Scripting.FileSystemObject")

On Error Resume Next
fso.MoveFolder Server.MapPath("drafts/2024"), Server.MapPath("archive/2024")
If Err.Number <> 0 Then
    Response.Write "MoveFolder failed: " & Err.Description
End If
On Error GoTo 0

Set fso = Nothing
%>
```

