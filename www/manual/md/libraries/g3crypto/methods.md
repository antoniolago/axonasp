# G3CRYPTO Methods

## Overview

This page summarizes every method exposed by `G3CRYPTO`.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Blake2b256(input)` | String | 64-character lowercase hexadecimal BLAKE2b-256 digest. |
| `Blake2b512(input)` | String | 128-character lowercase hexadecimal BLAKE2b-512 digest. |
| `ComputeHash(input [, algorithm])` | Array | Raw digest bytes as a zero-based VBScript byte array. |
| `GetBCryptCost()` | Integer | Current bcrypt work factor. |
| `HashPassword(password)` | String | bcrypt hash string, or empty string on failure. |
| `HmacSha256(data, key)` | String | 64-character lowercase hexadecimal HMAC-SHA256 digest. |
| `HmacSha512(data, key)` | String | 128-character lowercase hexadecimal HMAC-SHA512 digest. |
| `Initialize()` | Empty | Clears internal last-hash state. |
| `MD5(input)` | String | 32-character lowercase hexadecimal MD5 digest. |
| `Pbkdf2Sha256(password, salt [, iterations] [, keyLength])` | String | Lowercase hexadecimal derived key. |
| `RandomBase64([size])` | String | Base64-encoded cryptographically secure random bytes. |
| `RandomBytes([size])` | Array | Raw cryptographically secure random bytes as a VBScript byte array. |
| `RandomHex([size])` | String | Lowercase hexadecimal cryptographically secure random bytes. |
| `SetBCryptCost(cost)` | Boolean | `True` when cost is in range `4..31`; otherwise `False`. |
| `SHA1(input)` | String | 40-character lowercase hexadecimal SHA-1 digest. |
| `SHA256(input)` | String | 64-character lowercase hexadecimal SHA-256 digest. |
| `SHA3_256(input)` | String | 64-character lowercase hexadecimal SHA3-256 digest. |
| `SHA3_512(input)` | String | 128-character lowercase hexadecimal SHA3-512 digest. |
| `SHA384(input)` | String | 96-character lowercase hexadecimal SHA-384 digest. |
| `SHA512(input)` | String | 128-character lowercase hexadecimal SHA-512 digest. |
| `UUID()` | String | UUID v4 string, or empty string on random-source failure. |
| `VerifyPassword(password, hash)` | Boolean | `True` on bcrypt match; otherwise `False`. |

## Remarks

- Method names are case-insensitive.
- Digest methods return lowercase hexadecimal text unless documented otherwise.
- `ComputeHash` returns raw bytes and updates `Hash` when the algorithm is valid.
