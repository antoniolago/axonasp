# Get the bcrypt Cost

## Overview

Returns the current bcrypt work factor.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.GetBCryptCost()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **Integer**: Current bcrypt cost value.

## Remarks

- Default value is `10`.
- This value is the same value exposed by the `BCryptCost` property.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, cost
Set crypto = Server.CreateObject("G3CRYPTO")

cost = crypto.GetBCryptCost()
Response.Write "Current bcrypt cost: " & cost

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `GetBCryptCost`
- **Arguments**: None
- **Returns**: Integer — current bcrypt work factor
