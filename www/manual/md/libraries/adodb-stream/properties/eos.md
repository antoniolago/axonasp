# EOS Property

## Overview

Indicates whether current stream position is at or beyond end-of-stream.

## Syntax

```asp
value = stm.EOS
```

## Return Value

Boolean. Returns `True` when `Position >= Size`; otherwise returns `False`.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- This property is read-only.
- Use `EOS` in loops to stop reading safely.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "abc"
stm.Position = 0

Do While Not stm.EOS
	Response.Write stm.ReadText(1)
Loop

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: EOS
- Access: Read-only
- Type: Boolean