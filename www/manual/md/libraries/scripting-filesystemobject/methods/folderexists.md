# FolderExists Method

## Overview

Determines whether a folder exists at the specified path.

## Syntax

```asp
result = fso.FolderExists(folderspec)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| folderspec | String | Yes | The path to the folder to check. |

## Return Value

Returns **True** if a directory exists at the resolved path. Returns **False** if the directory does not exist, if the path resolves to a file, if the path cannot be resolved, or if no argument is supplied.

## How It Works

The path is resolved against the web root. The runtime calls `os.Stat` on the resolved path and returns True only when the call succeeds and the result is a directory entry. No error is raised; the method always returns a Boolean.

## Remarks

- `FolderExists` does not distinguish between a missing folder and a permission error. Both cases return False.
- To check for a file, use `FileExists` instead.

## Code Example

```asp
<%
Option Explicit
Dim fso, uploadDir
Set fso = Server.CreateObject("Scripting.FileSystemObject")

uploadDir = Server.MapPath("uploads")
If Not fso.FolderExists(uploadDir) Then
    fso.CreateFolder uploadDir
    Response.Write "Upload folder created."
Else
    Response.Write "Upload folder already exists."
End If

Set fso = Nothing
%>
```

