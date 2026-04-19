# Flush Method

## Overview

Commits pending stream writes in runtimes that buffer I/O.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Open the stream before calling `Flush`.

## Syntax

```asp
stm.Flush
```

## Parameters

This method does not accept parameters.

## Return Value

Empty. The method does not return a value.

## How It Works

- In current G3Pix AxonASP ADODB.Stream implementation, `Flush` is a compatibility no-op.
- The call does not modify `Position`, `Size`, or stream content.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Keep this call in legacy code paths that expect explicit flush points.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "buffered text"
stm.Flush

Response.Write "Flush executed"

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: Flush
- Arguments: none
- Returns: Empty