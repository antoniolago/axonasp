# LineSeparator Property

## Overview

Gets or sets the line separator written by `WriteText` when append-line mode is enabled.

## Syntax

```asp
value = stm.LineSeparator
stm.LineSeparator = newValue
```

## Return Value

Integer. Returns the active line separator flag.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- Common values are `10` (LF) and `13` (CR).
- This property is used only when `WriteText` is called with the optional append-line flag set to `1`.

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
stm.WriteText "line1", 1
stm.WriteText "line2", 1

Response.Write "LineSeparator: " & CStr(stm.LineSeparator)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: LineSeparator
- Access: Read/Write
- Type: Integer