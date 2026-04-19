# HashSize Property

## Overview

Returns the digest size in bits for the current internal hash context.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
sizeBits = crypto.HashSize
```

## Return Value

- **Integer**: Number of bits in the active digest context.
- **Integer `0`**: Returned when no digest context is available.

## Remarks

- When a default algorithm is configured for the object, this property reflects that algorithm's digest size.
- Otherwise, when raw digest bytes are stored, this property returns `Len(Hash) * 8`.
- Returns `0` when neither algorithm context nor stored hash bytes exist.

## API Reference

- **Object**: `G3CRYPTO`
- **Property**: `HashSize`
- **Access**: Read-only
- **Type**: Integer

## Code Example

```asp
<%
Option Explicit
Dim crypto
Set crypto = Server.CreateObject("G3CRYPTO")

crypto.ComputeHash "Bit Size Test", "sha256"
Response.Write "Hash Size: " & crypto.HashSize & " bits"

Set crypto = Nothing
%>
```
