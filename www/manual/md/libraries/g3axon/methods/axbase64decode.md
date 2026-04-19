# Decode a Base64 String

## Overview

Decodes a Base64-encoded string back to its original representation.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxBase64Decode(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The Base64-encoded string to decode. |

## Return Value

- **String**: The decoded original string.
- **String (empty)**: Returned when the input is not valid Base64.

## Remarks

- The decoded bytes are interpreted as a UTF-8 string.
- Padding characters (`=`) are handled automatically.
- To encode a string, use `AxBase64Encode`.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, decoded
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

decoded = ax.AxBase64Decode("SGVsbG8gV29ybGQ=")
Response.Write decoded
' Output: Hello World

decoded = ax.AxBase64Decode("!!!invalid!!!")
Response.Write "<br>" & Len(decoded)
' Output: 0 (empty string returned for invalid input)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxBase64Decode`
- **Arguments**: `str` (String, required)
- **Returns**: String — decoded original string, or empty string on invalid Base64 input