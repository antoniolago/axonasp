# OpenTextFile Method

## Overview

Opens a text file for reading, writing, or appending and returns a TextStream object.

## Syntax

```asp
Set ts = fso.OpenTextFile(filename [, iomode [, create]])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| filename | String | Yes | The full path to the text file to open. |
| iomode | Integer | No | The file access mode. 1 = ForReading (default), 2 = ForWriting, 8 = ForAppending. |
| create | Boolean | No | When True and iomode is 1 (ForReading), creates the file if it does not exist. Ignored for write and append modes, which always create the file. Defaults to False. |

## Return Value

Returns a **TextStream** object for the opened file. Returns **Empty** if the path cannot be resolved or if the OS rejects the open call (for example, the file does not exist and `create` is False for read mode).

## How It Works

The path is resolved against the web root. The runtime translates `iomode` into OS open flags:

- **1 (ForReading):** Opens with `O_RDONLY`. If `create` is True, `O_CREATE` is also set.
- **2 (ForWriting):** Opens with `O_WRONLY | O_CREATE | O_TRUNC`, replacing any existing content.
- **8 (ForAppending):** Opens with `O_WRONLY | O_CREATE | O_APPEND`, adding content at the end.

For write and append modes, the runtime creates any missing parent directories automatically.

## Remarks

- A TextStream opened in ForReading mode (1) rejects all write operations (`Write`, `WriteLine`, `WriteBlankLines`). Those calls return Empty silently.
- Always call `ts.Close` and `Set ts = Nothing` after use to release the file handle.
- Use `FileExists` before opening in read mode when you need to handle missing files without an error.

## Code Example

```asp
<%
Option Explicit
Dim fso, ts, line
Set fso = Server.CreateObject("Scripting.FileSystemObject")

' Append a log entry
Set ts = fso.OpenTextFile(Server.MapPath("logs/access.log"), 8, True)
ts.WriteLine Now & " - page loaded"
ts.Close
Set ts = Nothing

' Read the entire log
Set ts = fso.OpenTextFile(Server.MapPath("logs/access.log"), 1)
Do While Not ts.AtEndOfStream
    line = ts.ReadLine
    Response.Write Server.HtmlEncode(line) & "<br>"
Loop
ts.Close
Set ts = Nothing

Set fso = Nothing
%>
```

