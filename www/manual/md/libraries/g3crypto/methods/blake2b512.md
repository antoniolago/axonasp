# Compute a BLAKE2b-512 Digest

## Overview

Computes the BLAKE2b-512 digest of the input and returns the result as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.Blake2b512(input)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **input** | String or Array | No | Input data as text or a VBScript byte array. When omitted, the method hashes an empty string. |

## Return Value

- **String**: 128-character lowercase hexadecimal BLAKE2b-512 digest.

## Remarks

- BLAKE2b-512 is suitable for high-integrity scenarios requiring a 512-bit digest.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, digest
Set crypto = Server.CreateObject("G3CRYPTO")

digest = crypto.Blake2b512("Hello AxonASP")
Response.Write digest

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `Blake2b512`
- **Arguments**: `input` (String or Array, optional)
- **Returns**: String — 128-character lowercase hexadecimal digest
