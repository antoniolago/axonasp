# CreateFolder Method

## Overview

Creates the specified folder on disk and returns a Folder object for the newly created directory.

## Syntax

```asp
Set folder = fso.CreateFolder(folderspec)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| folderspec | String | Yes | The path of the folder to create. |

## Return Value

Returns a **Folder** object representing the newly created directory. Returns **Empty** if the path cannot be resolved or if `os.MkdirAll` fails.

## How It Works

The path is resolved against the web root. The runtime calls `os.MkdirAll`, which creates all missing intermediate directories in the hierarchy. If the folder already exists, the call succeeds and returns a Folder object for that existing directory. Use `Set` to capture the returned Folder object.

## Remarks

- All intermediate parent directories are created automatically.
- If the resolved path is empty or cannot be determined, the method returns Empty without raising an error.
- Use `FolderExists` first if you need to distinguish between creating a new folder and receiving an existing one.

## Code Example

```asp
<%
Option Explicit
Dim fso, fldr
Set fso = Server.CreateObject("Scripting.FileSystemObject")

If Not fso.FolderExists(Server.MapPath("uploads/2025")) Then
    Set fldr = fso.CreateFolder(Server.MapPath("uploads/2025"))
    Response.Write "Created: " & fldr.Path
    Set fldr = Nothing
End If

Set fso = Nothing
%>
```

