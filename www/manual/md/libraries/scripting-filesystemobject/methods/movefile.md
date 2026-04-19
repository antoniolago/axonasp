# MoveFile Method

## Overview

Moves a file from a source path to a destination path.

## Syntax

```asp
fso.MoveFile source, destination
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| source | String | Yes | The full path of the file to move. |
| destination | String | Yes | The full destination path, including the file name. |

## Return Value

Returns **Empty**. The method does not return a value.

## How It Works

Both paths are resolved against the web root. The runtime first attempts `os.Rename` for an atomic move. If the rename fails (for example, across different volumes), the runtime falls back to a copy-then-delete sequence. If the destination already exists, it is replaced. Parent directories of the destination are created automatically during the fallback path.

## Remarks

- If either path cannot be resolved, the operation is silently skipped.
- To move an entire directory, use `MoveFolder` instead.
- Use `On Error Resume Next` to handle errors gracefully at runtime.

## Code Example

```asp
<%
Option Explicit
Dim fso
Set fso = Server.CreateObject("Scripting.FileSystemObject")

On Error Resume Next
fso.MoveFile Server.MapPath("inbox/order.xml"), Server.MapPath("processed/order.xml")
If Err.Number <> 0 Then
    Response.Write "Move failed: " & Err.Description
End If
On Error GoTo 0

Set fso = Nothing
%>
```

