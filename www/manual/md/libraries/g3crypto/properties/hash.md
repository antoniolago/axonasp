# Hash Property

## Overview

Returns the raw byte array from the latest digest operation that updates internal hash state.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
byteArray = crypto.Hash
```

## Return Value

- **Array**: Zero-based VBScript byte array.
- **Array (empty)**: Returned when no digest bytes are currently stored.

## Remarks

- Updated by digest operations that store internal bytes, including `ComputeHash`, `HmacSha256`, `HmacSha512`, and `Pbkdf2Sha256`.
- Cleared by `Initialize`.
- Hex-returning digest methods such as `SHA256` return text and do not update this property.

## API Reference

- **Object**: `G3CRYPTO`
- **Property**: `Hash`
- **Access**: Read-only
- **Type**: Array (byte values)

## Code Example

```asp
<%
Option Explicit
Dim crypto, rawHash, i
Set crypto = Server.CreateObject("G3CRYPTO")

crypto.ComputeHash "Binary Output Test", "sha256"
rawHash = crypto.Hash

Response.Write "First 4 bytes: "
For i = 0 To 3
    Response.Write Hex(rawHash(i)) & " "
Next

Set crypto = Nothing
%>
```
