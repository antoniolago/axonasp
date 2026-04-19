# Compute a SHA-1 Digest

## Overview

Computes the SHA-1 digest of the input and returns the result as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.SHA1(input)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **input** | String or Array | No | Input data as text or a VBScript byte array. When omitted, the method hashes an empty string. |

## Return Value

- **String**: 40-character lowercase hexadecimal SHA-1 digest.

## Remarks

- SHA-1 is retained for compatibility and non-security-sensitive checks.
- Use SHA-256 or stronger algorithms for new security-critical features.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, digest
Set crypto = Server.CreateObject("G3CRYPTO")

digest = crypto.SHA1("Hello World")
Response.Write digest
' Output: 0a4d55a8d778e5022fab701977c5d840bbc486d0

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `SHA1`
- **Arguments**: `input` (String or Array, optional)
- **Returns**: String — 40-character lowercase hexadecimal digest
