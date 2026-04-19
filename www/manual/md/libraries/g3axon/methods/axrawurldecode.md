# Decode a Raw URL-Encoded String

## Overview

Decodes a URL-encoded string, treating `+` characters as spaces before applying standard percent-decoding.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxRawUrlDecode(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The raw URL-encoded string to decode. |

## Return Value

- **String**: The decoded string, with `+` characters replaced by spaces and percent-encoded sequences unescaped.

## Remarks

- This method first replaces each `+` with a space, then applies RFC 3986 percent-decoding. This matches the behavior of HTML form submissions using `application/x-www-form-urlencoded` encoding.
- Use `AxUrlDecode` when the input does not use `+` as a space.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, decoded
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

decoded = ax.AxRawUrlDecode("Hello+World%21")
Response.Write decoded
' Output: Hello World!

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxRawUrlDecode`
- **Arguments**: `str` (String, required)
- **Returns**: String — decoded string with `+` converted to spaces