# Use ADODB.Stream in G3Pix AxonASP

## Overview

Use `ADODB.Stream` to read, write, copy, and persist binary or text buffers with a cursor-based API.

## Prerequisites

- Create the stream with `Server.CreateObject("ADODB.Stream")`.
- Call `Open` before using read or write operations.
- Set `Type` and `Charset` before text operations when you need explicit encoding behavior.

## Syntax

```asp
Set stm = Server.CreateObject("ADODB.Stream")
```

## Return Value

- **Object**: Returns an `ADODB.Stream` object handle.

## How It Works

- Stream state is `0` when closed and `1` when open.
- `Read` returns byte-oriented data encoded as a VBScript-compatible byte string.
- `ReadText` decodes using the current `Charset`.
- `SaveToFile` and `LoadFromFile` operate inside AxonASP path resolution rules.

## Remarks

- Member names are case-insensitive.
- Unsupported stream members return `Empty`.
- `Flush` is implemented as a compatibility no-op.

## Example

```asp
<%
Option Explicit
Dim stm, textValue

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.Open

stm.WriteText "Hello from G3Pix AxonASP"
stm.Position = 0
textValue = stm.ReadText()

Response.Write textValue

stm.Close
Set stm = Nothing
%>
```

