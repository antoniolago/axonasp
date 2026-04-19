# Decode a URL-Encoded String

## Overview

Decodes a percent-encoded URL string produced by standard form submission or query string encoding.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxUrlDecode(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The URL-encoded string to decode. |

## Return Value

- **String**: The decoded string.
- **String (original input)**: Returned unchanged when the input contains malformed percent-encoding sequences.

## Remarks

- This method uses standard RFC 3986 percent-decoding. It does **not** convert `+` to a space. Use `AxRawUrlDecode` if the input uses `+` as a space character.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, decoded
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

decoded = ax.AxUrlDecode("Hello%20World%21")
Response.Write decoded
' Output: Hello World!

decoded = ax.AxUrlDecode("Hello+World")
Response.Write "<br>" & decoded
' Output: Hello+World (+ is not converted — use AxRawUrlDecode for that)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxUrlDecode`
- **Arguments**: `str` (String, required)
- **Returns**: String — decoded string, or original input on malformed encoding