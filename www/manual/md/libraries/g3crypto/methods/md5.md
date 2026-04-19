# Compute an MD5 Digest

## Overview

Computes the MD5 digest of the input and returns the result as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.MD5(input)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **input** | String or Array | No | Input data as text or a VBScript byte array. When omitted, the method hashes an empty string. |

## Return Value

- **String**: 32-character lowercase hexadecimal MD5 digest.

## Remarks

- MD5 is fast and useful for checksums but is not recommended for password hashing or collision-resistant security scenarios.
- The method accepts byte arrays and string inputs.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, digest
Set crypto = Server.CreateObject("G3CRYPTO")

digest = crypto.MD5("Hello World")
Response.Write digest
' Output: b10a8db164e0754105b7a99be72e3fe5

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `MD5`
- **Arguments**: `input` (String or Array, optional)
- **Returns**: String — 32-character lowercase hexadecimal digest
