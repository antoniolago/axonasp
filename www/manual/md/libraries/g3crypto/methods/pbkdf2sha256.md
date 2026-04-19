# Derive a Key with PBKDF2-SHA256

## Overview

Derives a key from a password and salt using PBKDF2 with HMAC-SHA256.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.Pbkdf2Sha256(password, salt [, iterations] [, keyLength])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **password** | String | Yes | Password or passphrase input. |
| **salt** | String | Yes | Salt value. Use a unique random salt per password. |
| **iterations** | Integer | No | Iteration count. Values less than or equal to `0` are replaced with `100000`. |
| **keyLength** | Integer | No | Derived key length in bytes. Values less than or equal to `0` are replaced with `32`. |

## Return Value

- **String**: Lowercase hexadecimal representation of the derived key. Length is `keyLength * 2` characters after normalization.
- **String (empty)**: Returned when required arguments are missing.

## Remarks

- On success, this method also updates the `Hash` property with raw derived-key bytes.
- PBKDF2 is intentionally CPU-intensive and suitable for password-based key derivation.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, salt, keyHex
Set crypto = Server.CreateObject("G3CRYPTO")

salt = "user-specific-random-salt"
keyHex = crypto.Pbkdf2Sha256("mySecretPassword", salt, 150000, 32)
Response.Write keyHex

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `Pbkdf2Sha256`
- **Arguments**: `password` (String, required), `salt` (String, required), `iterations` (Integer, optional), `keyLength` (Integer, optional)
- **Returns**: String — lowercase hexadecimal derived key, or empty string when required arguments are missing
