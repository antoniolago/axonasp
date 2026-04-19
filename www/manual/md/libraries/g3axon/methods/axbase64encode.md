# Encode a String to Base64

## Overview

Encodes a string to Base64 format using the standard RFC 4648 encoding.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxBase64Encode(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The string to encode. |

## Return Value

- **String**: The Base64-encoded representation of the input string.

## Remarks

- The input string is encoded as UTF-8 before Base64 encoding.
- Base64 encoding is commonly used to safely transmit or store binary or text data in text-based protocols.
- To reverse the operation, use `AxBase64Decode`.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, encoded
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

encoded = ax.AxBase64Encode("Hello World")
Response.Write encoded
' Output: SGVsbG8gV29ybGQ=

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxBase64Encode`
- **Arguments**: `str` (String, required)
- **Returns**: String — Base64-encoded representation of the input