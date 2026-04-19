# SkipLine Method

## Overview

Moves the stream position to the beginning of the next text line.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Use text mode (`Type = 2`) and open the stream.

## Syntax

```asp
stm.SkipLine
```

## Parameters

This method does not accept parameters.

## Return Value

Empty. The method does not return a value.

## How It Works

- Scans from current `Position` until it finds line separator bytes.
- Sets `Position` to the first character after the separator.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- In binary mode, line-based navigation is not meaningful.

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
stm.WriteText "first", 1
stm.WriteText "second", 1
stm.Position = 0
stm.SkipLine

Response.Write stm.ReadText(6)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: SkipLine
- Arguments: none
- Returns: Empty