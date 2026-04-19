# DeleteFolder Method

## Overview

Deletes the specified folder and all of its contents from disk.

## Syntax

```asp
fso.DeleteFolder folderspec
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| folderspec | String | Yes | The full path to the folder to delete. |

## Return Value

Returns **Empty**. The method does not return a value.

## How It Works

The path is resolved against the web root. The runtime first releases any open FSO handles (TextStream, File, or Folder objects) that point to paths within the target directory. It then sets file permissions to writable on all contained entries and removes the directory tree recursively. On Windows, the delete is retried up to five times with a short delay to absorb transient sharing locks.

## Error Conditions

| Condition | VBScript Error |
|---|---|
| Folder does not exist | 76 — Path not found |
| Path resolves to a file | 76 — Path not found |
| Access denied by the OS | 70 — Permission denied |

## Remarks

- All files and sub-folders inside the target are deleted. This operation cannot be undone.
- Use `FolderExists` before calling `DeleteFolder` to avoid errors when the folder may not exist.
- Use `On Error Resume Next` to handle deletion failures gracefully.

## Code Example

```asp
<%
Option Explicit
Dim fso, folderPath
Set fso = Server.CreateObject("Scripting.FileSystemObject")

folderPath = Server.MapPath("temp/session_cache")
If fso.FolderExists(folderPath) Then
    On Error Resume Next
    fso.DeleteFolder folderPath
    If Err.Number <> 0 Then
        Response.Write "Delete failed: " & Err.Description
    End If
    On Error GoTo 0
End If

Set fso = Nothing
%>
```

