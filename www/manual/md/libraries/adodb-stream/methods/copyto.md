# CopyTo Method

## Overview

Copies stream data from the current source position to another open ADODB.Stream object.

## Prerequisites

- Create both objects with `Server.CreateObject("ADODB.Stream")`.
- Open source and destination streams.
- Ensure both streams use compatible `Type` and encoding settings.

## Syntax

```asp
stm.CopyTo destination [, count]
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `destination` | Object | Yes | Destination ADODB.Stream object that receives copied bytes. |
| `count` | Integer | No | Number of bytes to copy. If omitted, copies all remaining bytes from source position. |

## Return Value

Empty. The method does not return a value.

## How It Works

- Reads bytes from source `Position`.
- Appends copied bytes at destination current `Position`.
- Advances source `Position` by copied byte count.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- The destination stream remains open and reusable after copy.

## Code Example

```asp
<%
Option Explicit
Dim sourceStm, targetStm

Set sourceStm = Server.CreateObject("ADODB.Stream")
Set targetStm = Server.CreateObject("ADODB.Stream")

sourceStm.Type = 2
sourceStm.Charset = "utf-8"
sourceStm.Open
sourceStm.WriteText "source payload"
sourceStm.Position = 0

targetStm.Type = 2
targetStm.Charset = "utf-8"
targetStm.Open
sourceStm.CopyTo targetStm
targetStm.Position = 0

Response.Write targetStm.ReadText()

sourceStm.Close
targetStm.Close
Set sourceStm = Nothing
Set targetStm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: CopyTo
- Arguments: `destination As ADODB.Stream`, `count As Integer` (optional)
- Returns: Empty