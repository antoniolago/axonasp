# Compute an MD5 Hash

## Overview

Computes the MD5 hash of a string and returns it as a lowercase hexadecimal string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxMD5(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The input string to hash. |

## Return Value

- **String**: A 32-character lowercase hexadecimal MD5 digest.

## Remarks

- MD5 is a fast, non-cryptographic-strength hash. Use it for checksums and non-security-sensitive identifiers, not for password storage.
- The input string is encoded as UTF-8 before hashing.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, hash
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

hash = ax.AxMD5("AxonASP")
Response.Write hash
' Output: 3e3a3e7f84bbf16cce4ad33fd9d68aca (example — actual value depends on input)

hash = ax.AxMD5("admin")
Response.Write "<br>" & hash
' Output: 21232f297a57a5a743894a0e4a801fc3

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxMD5`
- **Arguments**: `str` (String, required)
- **Returns**: String — 32-character lowercase hexadecimal MD5 hash