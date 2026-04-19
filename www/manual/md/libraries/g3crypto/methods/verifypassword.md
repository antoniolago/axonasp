# Verify a Password Against a bcrypt Hash

## Overview

Checks whether a plain-text password matches a stored bcrypt hash.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.VerifyPassword(password, hash)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **password** | String | Yes | User-supplied plain-text password. |
| **hash** | String | Yes | Stored bcrypt hash string. |

## Return Value

- **Boolean `True`**: Password matches the bcrypt hash.
- **Boolean `False`**: Password does not match, hash is invalid, or required arguments are missing.

## Remarks

- This method is the recommended password verification path for authentication flows.
- bcrypt hash parsing and verification are handled internally.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, storedHash, userPass
Set crypto = Server.CreateObject("G3CRYPTO")

storedHash = "$2a$10$WmEynFf7ivBvJ9fD2X4aj.7YyUw8lnjxudlEE4u7YwY3QJ7V6dNlm"
userPass = Request.Form("password")

If crypto.VerifyPassword(userPass, storedHash) Then
    Response.Write "Login Success"
Else
    Response.Write "Invalid Credentials"
End If

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `VerifyPassword`
- **Arguments**: `password` (String, required), `hash` (String, required)
- **Returns**: Boolean — `True` when password matches; `False` otherwise
