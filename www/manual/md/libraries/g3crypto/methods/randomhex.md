# Generate a Secure Random Hex String

## Overview

Generates cryptographically secure random bytes and returns them as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.RandomHex([size])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **size** | Integer | No | Number of random bytes to generate. Default is `32`. Negative values are normalized to `0`. |

## Return Value

- **String**: Lowercase hexadecimal string with `size * 2` characters after normalization.
- **String (empty)**: Returned when `size` is `0` or random generation fails.

## Remarks

- This method is useful for token generation where hex encoding is preferred.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, token
Set crypto = Server.CreateObject("G3CRYPTO")

token = crypto.RandomHex(16)
Response.Write token
' 32 hex characters

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `RandomHex`
- **Arguments**: `size` (Integer, optional)
- **Returns**: String — lowercase hex output, or empty string on failure/zero length
