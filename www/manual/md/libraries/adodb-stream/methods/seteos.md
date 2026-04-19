# SetEOS Method

## Overview

Truncates the stream so end-of-stream matches the current cursor position.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Open the stream before truncation.

## Syntax

```asp
stm.SetEOS
```

## Parameters

This method does not accept parameters.

## Return Value

Empty. The method does not return a value.

## How It Works

- Removes all bytes after current `Position`.
- Updates `Size` to the new truncated length.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Use this method to discard trailing buffer content after partial edits.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "abcdef"
stm.Position = 3
stm.SetEOS
stm.Position = 0

Response.Write stm.ReadText()

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: SetEOS
- Arguments: none
- Returns: Empty