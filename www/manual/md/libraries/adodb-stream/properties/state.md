# State Property

## Overview

Returns whether the stream is open or closed.

## Syntax

```asp
value = stm.State
```

## Return Value

Integer. Returns `0` when the stream is closed and `1` when the stream is open.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- This property is read-only.
- Check `State` before calling read and write methods.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
Response.Write "Before open: " & CStr(stm.State) & "<br>"

stm.Open
Response.Write "After open: " & CStr(stm.State) & "<br>"

stm.Close
Response.Write "After close: " & CStr(stm.State)

Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: State
- Access: Read-only
- Type: Integer (`0` closed, `1` open)