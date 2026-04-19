# Hash a Password with bcrypt

## Overview

Generates a bcrypt hash string for a plain-text password using the current bcrypt cost configuration.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.HashPassword(password)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **password** | String | No | Plain-text password to hash. When omitted, an empty string is hashed. |

## Return Value

- **String**: bcrypt hash string in the `$2a$<cost>$...` format.
- **String (empty)**: Returned when bcrypt hashing fails.

## Remarks

- The current `BCryptCost` value controls the bcrypt work factor.
- Use `VerifyPassword` to validate user input against a stored bcrypt hash.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, hashed
Set crypto = Server.CreateObject("G3CRYPTO")

hashed = crypto.HashPassword("mySecretPassword")
Response.Write hashed

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `HashPassword`
- **Arguments**: `password` (String, optional)
- **Returns**: String — bcrypt hash string, or empty string on failure
