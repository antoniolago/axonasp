# GetTempName Method

## Overview

Generates and returns a unique temporary file name. The file is not created on disk.

## Syntax

```asp
result = fso.GetTempName()
```

## Parameters

None.

## Return Value

Returns a **String** containing a unique temporary file name in the format `radXXXXXXXXXX.axon.tmp`, where `X` characters are hexadecimal digits derived from the current time in nanoseconds.

## How It Works

The method formats the current `time.Now().UnixNano()` value as uppercase hexadecimal and embeds it into the `rad%X.axon.tmp` pattern. The result is a name-only string, not a full path. No file is created, and no disk access is performed.

## Remarks

- The returned name is not a full path. Combine it with `BuildPath` and a directory path (such as the system temp directory from `GetSpecialFolder(2)`) before creating the file.
- Because the name is based on the current nanosecond timestamp, normal web request sequencing makes collisions extremely unlikely, but not impossible under heavy concurrent load. Verify file non-existence with `FileExists` before use if strict uniqueness is required.

## Code Example

```asp
<%
Option Explicit
Dim fso, tempName, tempPath, ts
Set fso = Server.CreateObject("Scripting.FileSystemObject")

tempName = fso.GetTempName()
tempPath = fso.BuildPath(fso.GetSpecialFolder(2), tempName)

Set ts = fso.CreateTextFile(tempPath, False)
ts.Write "temporary data"
ts.Close
Set ts = Nothing

Response.Write "Temp file: " & tempPath

fso.DeleteFile tempPath
Set fso = Nothing
%>
```

