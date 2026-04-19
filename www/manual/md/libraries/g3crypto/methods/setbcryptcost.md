# Set the bcrypt Cost

## Overview

Sets the bcrypt work factor used by `HashPassword`.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.SetBCryptCost(cost)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **cost** | Integer | Yes | bcrypt work factor. Valid range is `4` to `31`. |

## Return Value

- **Boolean `True`**: Cost was accepted and applied.
- **Boolean `False`**: Cost is outside `4..31` or argument is missing.

## Remarks

- Default bcrypt cost is `10`.
- Higher cost increases password hashing time and CPU usage.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, ok
Set crypto = Server.CreateObject("G3CRYPTO")

ok = crypto.SetBCryptCost(12)
If ok Then
    Response.Write "bcrypt cost updated to 12"
Else
    Response.Write "Invalid bcrypt cost"
End If

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `SetBCryptCost`
- **Arguments**: `cost` (Integer, required)
- **Returns**: Boolean — `True` on success, `False` on invalid value
