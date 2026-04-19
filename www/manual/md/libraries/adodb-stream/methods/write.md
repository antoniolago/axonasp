# Write Method

## Overview

Writes binary data at the current stream position.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Set `Type = 1` for binary mode.
- Open the stream before writing.

## Syntax

```asp
stm.Write data
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `data` | String | Yes | Byte-string payload to write into the stream buffer. |

## Return Value

Empty. The method does not return a value.

## How It Works

- Writes bytes starting at current `Position`.
- Advances `Position` by number of bytes written.
- Expands `Size` when writing beyond current end.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Use `WriteText` for text-mode operations.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 1
stm.Open
stm.Write ChrB(&HDE) & ChrB(&HAD) & ChrB(&HBE) & ChrB(&HEF)

Response.Write "Size after write: " & CStr(stm.Size)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: Write
- Arguments: `data As String`
- Returns: Empty