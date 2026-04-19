# Compute a Hash as a Byte Array

## Overview

Computes a hash digest and returns the raw digest bytes as a VBScript array.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.ComputeHash(input [, algorithm])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **input** | String or Array | No | Input data as text or a VBScript byte array. When omitted, an empty string is hashed. |
| **algorithm** | String | No | Hash algorithm name. If omitted on a standard `G3CRYPTO` instance, `sha256` is used. |

Supported algorithm names: `md5`, `sha1`, `sha256`, `sha384`, `sha512`, `sha3_256`, `sha3_512`, `blake2b256`, `blake2b512`.

## Return Value

- **Array**: Zero-based VBScript byte array containing the digest.
- **Array (empty)**: Returned when the algorithm name is not recognized.

## Remarks

- This method updates the `Hash` property with the same bytes when a valid algorithm is used.
- When the algorithm is invalid, `Hash` is not updated.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, hashBytes
Set crypto = Server.CreateObject("G3CRYPTO")

hashBytes = crypto.ComputeHash("Hello World", "sha256")
Response.Write "Digest bytes: " & (UBound(hashBytes) + 1)

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `ComputeHash`
- **Arguments**: `input` (String or Array, optional), `algorithm` (String, optional)
- **Returns**: Array — digest bytes, or empty array for unsupported algorithm
