# Generate Secure Random Bytes

## Overview

Generates cryptographically secure random data and returns it as a VBScript byte array.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.RandomBytes([size])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **size** | Integer | No | Number of bytes to generate. Default is `32`. Negative values are normalized to `0`. |

## Return Value

- **Array**: Zero-based VBScript byte array containing random bytes.
- **Array (empty)**: Returned when `size` is `0` or when random generation fails.

## Remarks

- Use this method for salts, nonces, key material, and opaque tokens.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, bytes
Set crypto = Server.CreateObject("G3CRYPTO")

bytes = crypto.RandomBytes(16)
If UBound(bytes) >= 0 Then
	Response.Write "First byte: " & bytes(0)
End If

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `RandomBytes`
- **Arguments**: `size` (Integer, optional)
- **Returns**: Array — random bytes, or empty array on failure/zero length
