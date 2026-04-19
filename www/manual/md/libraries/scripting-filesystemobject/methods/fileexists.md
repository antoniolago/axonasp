# FileExists Method

## Overview

Determines whether a file exists at the specified path.

## Syntax

```asp
result = fso.FileExists(filespec)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| filespec | String | Yes | The path to the file to check. |

## Return Value

Returns **True** if a file exists at the resolved path and the entry is not a directory. Returns **False** if the file does not exist, if the path resolves to a directory, if the path cannot be resolved, or if no argument is supplied.

## How It Works

The path is resolved against the web root. The runtime calls `os.Stat` on the resolved path and returns True only when the call succeeds and the result is not a directory entry. No error is raised; the method always returns a Boolean.

## Remarks

- `FileExists` does not distinguish between a missing file and a permission error. Both cases return False.
- To check for a directory, use `FolderExists` instead.

## Code Example

```asp
<%
Option Explicit
Dim fso, configPath
Set fso = Server.CreateObject("Scripting.FileSystemObject")

configPath = Server.MapPath("config/settings.ini")
If fso.FileExists(configPath) Then
    Response.Write "Config file found."
Else
    Response.Write "Config file not found."
End If

Set fso = Nothing
%>
```

