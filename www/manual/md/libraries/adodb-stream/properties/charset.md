# Charset Property

## Overview

Gets or sets the text encoding used by `ReadText` and `WriteText`.

## Syntax

```asp
value = stm.Charset
stm.Charset = newValue
```

## Return Value

String. Returns the active charset name.

## Remarks

- Property names are case-insensitive in G3Pix AxonASP.
- This property affects text mode (`Type = 2`) operations.
- New stream objects default to `unicode`.
- Assigning an empty charset value resets to `utf-8` in current runtime behavior.

## Code Example

```asp
<%
Option Explicit
Dim stm

Set stm = Server.CreateObject("ADODB.Stream")
stm.Type = 2
stm.Charset = "utf-8"
stm.Open
stm.WriteText "cafe"

Response.Write "Charset: " & stm.Charset

stm.Close
Set stm = Nothing
%>
```

## API Reference

- Object: ADODB.Stream
- Property: Charset
- Access: Read/Write
- Type: String