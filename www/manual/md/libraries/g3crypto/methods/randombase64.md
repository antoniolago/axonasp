# Generate a Secure Random Base64 String

## Overview

Generates cryptographically secure random bytes and returns them as a Base64 string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.RandomBase64([size])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **size** | Integer | No | Number of random bytes to generate. Default is `32`. Negative values are normalized to `0`. |

## Return Value

- **String**: Base64-encoded random data.
- **String (empty)**: Returned when `size` is `0` or random generation fails.

## Remarks

- Base64 output length depends on the byte size and padding.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, token
Set crypto = Server.CreateObject("G3CRYPTO")

token = crypto.RandomBase64(16)
Response.Write token

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `RandomBase64`
- **Arguments**: `size` (Integer, optional)
- **Returns**: String — Base64 output, or empty string on failure/zero length
