# ReadText Method

## Overview

Reads text from the current stream position using the configured character encoding.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Set `Type = 2` for text mode.
- Set `Charset` if you need a specific encoding.
- Open the stream before reading.

## Syntax

```asp
text = stm.ReadText([numChars])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `numChars` | Integer | No | Number of characters to read. If omitted, reads all remaining text to end of stream. |

## Return Value

String. Returns decoded text from the current position. Returns an empty string when the stream is closed, at end of stream, or no text remains.

## How It Works

- Decodes bytes according to `Charset`.
- Moves `Position` forward by consumed bytes.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Use `Read` for binary payloads.

## Code Example

```asp
<%
Option Explicit
Dim stm, part

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.Open
stm.WriteText "G3Pix AxonASP Stream"
stm.Position = 0

part = stm.ReadText(5)
Response.Write part

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: ReadText
- Arguments: `numChars As Integer` (optional)
- Returns: String