# WriteText Method

## Overview

Writes text data to the stream buffer using the current `Charset`.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Set `Type = 2` for text mode.
- Open the stream before writing.

## Syntax

```asp
stm.WriteText text [, writeLine]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `text` | String | Yes | Text to write at current stream position. |
| `writeLine` | Integer | No | When `1`, appends the configured line separator after `text`. Any other value writes only `text`. |

## Return Value

Empty. The method does not return a value.

## How It Works

- Encodes the input with `Charset`.
- Writes bytes at current `Position`.
- Advances `Position` by bytes written.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Use `Write` for binary payloads.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.LineSeparator = 10
stm.Open
stm.WriteText "Header", 1
stm.WriteText "Body"

Response.Write "Size: " & CStr(stm.Size)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: WriteText
- Arguments: `text As String`, `writeLine As Integer` (optional)
- Returns: Empty