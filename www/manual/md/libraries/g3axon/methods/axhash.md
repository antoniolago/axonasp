# Compute a String Hash by Algorithm

## Overview

Computes the hash of a string using the specified cryptographic algorithm and returns the result as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxHash(algo, str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **algo** | String | Yes | The hashing algorithm. Supported values: `"md5"`, `"sha1"`, `"sha256"`. |
| **str** | String | Yes | The input string to hash. |

## Return Value

- **String**: A lowercase hexadecimal digest. Length depends on the algorithm: 32 characters for MD5, 40 for SHA-1, 64 for SHA-256.
- **String (empty)**: Returned when an unsupported algorithm name is provided.

## Remarks

- Algorithm names are matched case-insensitively.
- The input string is encoded as UTF-8 before hashing.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxHash("md5", "hello") & "<br>"
' Output: 5d41402abc4b2a76b9719d911017c592

Response.Write ax.AxHash("sha256", "hello") & "<br>"
' Output: 2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824

Response.Write ax.AxHash("invalid", "hello") & "<br>"
' Output: (empty string)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxHash`
- **Arguments**: `algo` (String, required), `str` (String, required)
- **Returns**: String — lowercase hexadecimal hash, or empty string for unsupported algorithms