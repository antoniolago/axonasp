# Close Method

## Overview

Closes the stream and releases access to its current buffer.

## Prerequisites

- Create the object with `Server.CreateObject("ADODB.Stream")`.
- Open the stream before calling `Close` when you need deterministic cleanup.

## Syntax

```asp
stm.Close
```

## Parameters

This method does not accept parameters.

## Return Value

Empty. The method does not return a value.

## How It Works

- Sets `State` to `0` (closed).
- Keeps object instance valid so you can call `Open` again.

## Remarks

- Method names are case-insensitive in G3Pix AxonASP.
- Calling `Close` on an already closed stream is safe.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "temporary"
stm.Close

Response.Write "State after close: " & CStr(stm.State)

Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Method: Close
- Arguments: none
- Returns: Empty