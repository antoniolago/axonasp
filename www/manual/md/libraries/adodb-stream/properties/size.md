# Size Property

## Overview

Returns the current stream length in bytes.

## Syntax

```asp
value = stm.Size
```

## Return Value

Integer. Returns total byte count stored in the stream buffer.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- This property is read-only.
- `Size` changes after `Write`, `WriteText`, `LoadFromFile`, `CopyTo`, or `SetEOS`.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Open
stm.WriteText "hello"

Response.Write "Size in bytes: " & CStr(stm.Size)

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: Size
- Access: Read-only
- Type: Integer