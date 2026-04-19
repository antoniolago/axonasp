# Open Method

## Overview

Opens the stream and initializes its internal cursor so read and write operations can run.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Set `Type` and optional text settings such as `Charset` before opening the stream.

## Syntax

```asp
stm.Open
```

## Parameters

This method does not accept parameters.

## Return Value

Empty. The method does not return a value.

## How It Works

- Changes `State` from `0` (closed) to `1` (open).
- Resets `Position` to the beginning of the in-memory buffer.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Calling `Open` on an already open stream keeps the stream available for I/O.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.Open

Response.Write "State: " & CStr(stm.State)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: Open
- Arguments: none
- Returns: Empty