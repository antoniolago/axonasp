# BCryptCost Property

## Overview

Gets or sets the bcrypt work factor used by `HashPassword`.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
' Get current cost
cost = crypto.BCryptCost

' Set new cost
crypto.BCryptCost = 12
```

## Return Value

- **Integer**: Current bcrypt work factor.

## Remarks

- Default value is `10`.
- Valid range is `4..31`.
- Setting values outside `4..31` has no effect.
- Higher values increase CPU time for hashing and verification.

## API Reference

- **Object**: `G3CRYPTO`
- **Property**: `BCryptCost`
- **Access**: Read/Write
- **Type**: Integer
- **Valid Set Range**: `4..31`

## Code Example

```asp
<%
Option Explicit
Dim crypto
Set crypto = Server.CreateObject("G3CRYPTO")

crypto.BCryptCost = 12
Response.Write "New BCrypt Cost: " & crypto.BCryptCost

Set crypto = Nothing
%>
```
