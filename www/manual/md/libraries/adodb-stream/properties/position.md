# Position Property

## Overview

Gets or sets the current cursor position in the stream buffer.

## Syntax

```asp
value = stm.Position
stm.Position = newValue
```

## Return Value

Integer. Returns the current byte offset from the start of the stream.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- Valid range is `0` to `Size`.
- Assignments below `0` clamp to `0`; assignments above `Size` clamp to `Size`.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "abcdef"
stm.Position = 2

Response.Write "Current position: " & CStr(stm.Position)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: Position
- Access: Read/Write
- Type: Integer