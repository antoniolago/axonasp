# Reset the Internal Hash State

## Overview

Clears the internal last-hash buffer maintained by the current `G3CRYPTO` object instance.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.Initialize()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **Empty**: Always returns `Empty`.

## Remarks

- This method clears the value returned by the `Hash` property.
- This method does not change `BCryptCost`.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, bytes
Set crypto = Server.CreateObject("G3CRYPTO")

bytes = crypto.ComputeHash("Some data", "sha256")
crypto.Initialize()

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `Initialize`
- **Arguments**: None
- **Returns**: Empty
