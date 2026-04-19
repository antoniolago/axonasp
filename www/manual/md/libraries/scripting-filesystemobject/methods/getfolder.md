# GetFolder Method

## Overview

Returns a Folder object for an existing folder at the specified path.

## Syntax

```asp
Set fldr = fso.GetFolder(folderspec)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| folderspec | String | Yes | The full path to the folder. |

## Return Value

Returns a **Folder** object representing the directory at the resolved path. Use `Set` for assignment. Raises a VBScript error if the folder does not exist or cannot be accessed.

## Error Conditions

| Condition | VBScript Error |
|---|---|
| Folder does not exist | 76 — Path not found |
| Path resolves to a file | 76 — Path not found |
| Access denied by the OS | 70 — Permission denied |

## How It Works

The path is resolved against the web root. The runtime calls `os.Stat` to confirm that the path exists and is a directory. On success, it stores a native `fsoKindFolder` object internally and returns the handle. The Folder object exposes properties such as `Name`, `Path`, `Files`, `SubFolders`, `Size`, `DateLastModified`, and methods including `Copy`, `Move`, `Delete`, and `CreateTextFile`.

## Remarks

- Always use `Set` to capture the returned Folder object.
- Call `Set fldr = Nothing` when the Folder object is no longer needed.
- To check existence before calling `GetFolder`, use `FolderExists`.

## Code Example

```asp
<%
Option Explicit
Dim fso, fldr
Set fso = Server.CreateObject("Scripting.FileSystemObject")

Set fldr = fso.GetFolder(Server.MapPath("uploads"))
Response.Write fldr.Name & " — " & fldr.Size & " bytes total"
Set fldr = Nothing

Set fso = Nothing
%>
```

