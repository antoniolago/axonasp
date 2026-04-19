# DeleteFile Method

## Overview

Deletes the specified file from disk.

## Syntax

```asp
fso.DeleteFile filespec
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| filespec | String | Yes | The full path to the file to delete. |

## Return Value

Returns **Empty**. The method does not return a value.

## How It Works

The path is resolved against the web root. If the path resolves to an existing file, the runtime removes it. If the target is a directory instead of a file, the runtime raises VBScript error 53 (File not found). Any open TextStream handles rooted at the same path are closed and released before the delete is attempted.

## Error Conditions

| Condition | VBScript Error |
|---|---|
| File does not exist | 53 — File not found |
| Target is a directory | 53 — File not found |
| Access denied by the OS | 70 — Permission denied |

## Remarks

- Use `FileExists` before calling `DeleteFile` if you want to avoid raising an error when the file may not exist.
- Use `On Error Resume Next` to handle deletion failures gracefully.

## Code Example

```asp
<%
Option Explicit
Dim fso, filePath
Set fso = Server.CreateObject("Scripting.FileSystemObject")

filePath = Server.MapPath("temp/cache.tmp")
If fso.FileExists(filePath) Then
    On Error Resume Next
    fso.DeleteFile filePath
    If Err.Number <> 0 Then
        Response.Write "Delete failed: " & Err.Description
    End If
    On Error GoTo 0
End If

Set fso = Nothing
%>
```

