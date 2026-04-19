# Type Property

## Overview

Gets or sets the stream content mode.

## Syntax

```asp
value = stm.Type
stm.Type = newValue
```

## Return Value

Integer. Returns `1` for binary mode or `2` for text mode.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- Set `Type = 1` before binary `Read` and `Write` operations.
- Set `Type = 2` before `ReadText` and `WriteText` operations.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "text payload"
Response.Write "Type: " & CStr(stm.Type)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: Type
- Access: Read/Write
- Type: Integer (`1` binary, `2` text)