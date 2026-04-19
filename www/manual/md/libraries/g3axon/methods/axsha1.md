# Compute a SHA-1 Hash

## Overview

Computes the SHA-1 hash of a string and returns it as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxSHA1(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The input string to hash. |

## Return Value

- **String**: A 40-character lowercase hexadecimal SHA-1 digest.

## Remarks

- SHA-1 produces a 160-bit hash. It is suitable for checksums and integrity verification but is not recommended for new security-sensitive applications.
- The input string is encoded as UTF-8 before hashing.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, hash
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

hash = ax.AxSHA1("test")
Response.Write hash
' Output: a94a8fe5ccb19ba61c4c0873d391e987982fbbd3

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxSHA1`
- **Arguments**: `str` (String, required)
- **Returns**: String — 40-character lowercase hexadecimal SHA-1 hash