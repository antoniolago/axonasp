# Compute an HMAC-SHA512 Signature

## Overview

Computes an HMAC signature using SHA-512 and returns the digest as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.HmacSha512(data, key)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **data** | String | Yes | Message payload to sign. |
| **key** | String | Yes | Secret key for HMAC generation. |

## Return Value

- **String**: 128-character lowercase hexadecimal HMAC-SHA512 digest.
- **String (empty)**: Returned when required arguments are missing.

## Remarks

- On success, this method also updates the `Hash` property with raw digest bytes.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, signature
Set crypto = Server.CreateObject("G3CRYPTO")

signature = crypto.HmacSha512("Hello World", "mySecretKey")
Response.Write signature

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `HmacSha512`
- **Arguments**: `data` (String, required), `key` (String, required)
- **Returns**: String — 128-character lowercase hexadecimal digest, or empty string when arguments are missing
