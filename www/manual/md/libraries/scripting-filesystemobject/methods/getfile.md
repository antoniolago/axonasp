# GetFile Method

## Overview

Returns a File object for an existing file at the specified path.

## Syntax

```asp
Set f = fso.GetFile(filespec)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| filespec | String | Yes | The full path to the file. |

## Return Value

Returns a **File** object representing the file at the resolved path. Use `Set` for assignment. Raises a VBScript error if the file does not exist or cannot be accessed.

## Error Conditions

| Condition | VBScript Error |
|---|---|
| File does not exist | 53 — File not found |
| Path resolves to a directory | 53 — File not found |
| Access denied by the OS | 70 — Permission denied |

## How It Works

The path is resolved against the web root. The runtime calls `os.Stat` to confirm that the path exists and is a file. On success, it stores a native `fsoKindFile` object internally and returns the handle. The File object exposes properties such as `Name`, `Size`, `Path`, `DateLastModified`, and methods including `Copy`, `Move`, `Delete`, and `OpenAsTextStream`.

## Remarks

- Always use `Set` to capture the returned File object.
- Call `Set f = Nothing` when the File object is no longer needed.
- To check existence before calling `GetFile`, use `FileExists`.

## Code Example

```asp
<%
Option Explicit
Dim fso, f
Set fso = Server.CreateObject("Scripting.FileSystemObject")

Set f = fso.GetFile(Server.MapPath("data/report.csv"))
Response.Write f.Name & " — " & f.Size & " bytes" & "<br>"
Response.Write "Modified: " & f.DateLastModified
Set f = Nothing

Set fso = Nothing
%>
```

