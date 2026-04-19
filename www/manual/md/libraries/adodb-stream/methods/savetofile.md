# SaveToFile Method

## Overview

Persists the current stream buffer to disk.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Open and populate the stream before saving.

## Syntax

```asp
stm.SaveToFile path [, options]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `path` | String | Yes | Destination file path. |
| `options` | Integer | No | Save option flag. `1` creates a new file and fails if it exists. `2` overwrites existing file content. Default is `2`. |

## Return Value

Empty. The method does not return a value.

## How It Works

- Writes the entire stream buffer to the target file.
- Does not close the stream after saving.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Use binary mode for raw bytes and text mode for encoded text payloads.

## Code Example

```asp
<%
Option Explicit
Dim stm, outPath

outPath = Server.MapPath("./output/report.txt")
Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.Open
stm.WriteText "Export generated"
stm.SaveToFile outPath, 2

Response.Write "Saved to disk"

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: SaveToFile
- Arguments: `path As String`, `options As Integer` (optional)
- Returns: Empty