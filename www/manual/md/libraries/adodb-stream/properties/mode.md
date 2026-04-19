# Mode Property

## Overview

Gets or sets stream access mode flags.

## Syntax

```asp
value = stm.Mode
stm.Mode = newValue
```

## Return Value

Integer. Returns the current mode flag value.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- This property is exposed for ADODB compatibility and can be assigned before opening the stream.
- Runtime enforcement of specific lock/share semantics can vary by host environment.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Mode = 3
stm.Open

Response.Write "Mode: " & CStr(stm.Mode)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: Mode
- Access: Read/Write
- Type: Integer