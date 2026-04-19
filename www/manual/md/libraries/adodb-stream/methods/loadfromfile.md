# LoadFromFile Method

## Overview

Loads file content into the stream buffer.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Open the stream before loading.

## Syntax

```asp
stm.LoadFromFile path
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `path` | String | Yes | Absolute or mapped file path to read. |

## Return Value

Empty. The method does not return a value.

## How It Works

- Replaces current in-memory stream data with file bytes.
- Sets `Position` to `0` after loading.
- Updates `Size` to loaded byte length.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- In text mode, later `ReadText` operations decode bytes using current `Charset`.

## Code Example

```asp
<%
Option Explicit
Dim stm, filePath

filePath = Server.MapPath("./data/sample.txt")
Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.Open
stm.LoadFromFile filePath

Response.Write "Loaded bytes: " & CStr(stm.Size)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: LoadFromFile
- Arguments: `path As String`
- Returns: Empty