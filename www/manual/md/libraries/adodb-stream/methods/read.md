# Read Method

## Overview

Reads binary data from the current stream position.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Set `Type = 1` for binary mode.
- Open the stream and ensure data exists in the buffer.

## Syntax

```asp
data = stm.Read([numBytes])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `numBytes` | Integer | No | Number of bytes to read from the current `Position`. If omitted, reads all remaining bytes until end of stream. |

## Return Value

String. Returns a byte-string payload containing the bytes read. Returns an empty string when the stream is closed, at end of stream, or no bytes are available.

## How It Works

- Reads from current `Position`.
- Advances `Position` by the number of bytes returned.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Use `ReadText` instead of `Read` when `Type = 2` and text decoding is required.

## Code Example

```asp
<%
Option Explicit
Dim stm, bytesChunk

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 1
stm.Open
stm.Write ChrB(1) & ChrB(2) & ChrB(3) & ChrB(4)
stm.Position = 0

bytesChunk = stm.Read(2)
Response.Write "Bytes read: " & CStr(LenB(bytesChunk))

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: Read
- Arguments: `numBytes As Integer` (optional)
- Returns: String (byte-string payload)