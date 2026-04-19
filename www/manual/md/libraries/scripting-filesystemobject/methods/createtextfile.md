# CreateTextFile Method

## Overview

Creates a new text file on disk and returns a TextStream object opened for writing.

## Syntax

```asp
Set ts = fso.CreateTextFile(filename [, overwrite])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| filename | String | Yes | The full path of the file to create. |
| overwrite | Boolean | No | Set to True (default) to truncate and overwrite an existing file. Set to False to fail if the file already exists. |

## Return Value

Returns a **TextStream** object opened for writing (mode 2). Returns **Empty** if the path cannot be resolved, if `overwrite` is False and the file already exists, or if the OS rejects the file creation.

## How It Works

The path is resolved against the web root. The runtime opens the file with `O_CREATE | O_WRONLY`. When `overwrite` is True, `O_TRUNC` is added to clear any existing content. When `overwrite` is False, `O_EXCL` is added so the open call fails if the file exists. The resulting TextStream starts at position line 1, column 1.

## Remarks

- The returned TextStream is write-only. Calling read methods on it returns Empty or empty String.
- Always call `ts.Close` and then `Set ts = Nothing` when you are finished writing.
- If the parent directory does not exist, file creation fails and the method returns Empty.

## Code Example

```asp
<%
Option Explicit
Dim fso, ts
Set fso = Server.CreateObject("Scripting.FileSystemObject")

Set ts = fso.CreateTextFile(Server.MapPath("output/log.txt"), True)
If Not IsNull(ts) And Not IsEmpty(ts) Then
    ts.WriteLine "Log started: " & Now
    ts.Close
    Set ts = Nothing
End If

Set fso = Nothing
%>
```

