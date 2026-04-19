# Check If a Value Is Empty

## Overview

Determines whether a value is considered empty under extended criteria that covers uninitialized variables, null values, zero-like values, and empty strings.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxEmpty(value)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **value** | Variant | Yes | The value to test for emptiness. |

## Return Value

- **Boolean `True`**: The value is `Empty`, `Null`, an empty string (`""`), Integer `0`, Double `0.0`, or Boolean `False`.
- **Boolean `False`**: The value is any other non-empty, non-zero value.

## Remarks

- This method provides a single call to replace multiple `IsEmpty`, `IsNull`, and zero-comparison checks.
- Use `AxIsSet` for the inverse check (value is initialized and not null).
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxEmpty("") & "<br>"         ' True
Response.Write ax.AxEmpty(0) & "<br>"          ' True
Response.Write ax.AxEmpty(False) & "<br>"      ' True
Response.Write ax.AxEmpty("hello") & "<br>"    ' False
Response.Write ax.AxEmpty(1) & "<br>"          ' False

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxEmpty`
- **Arguments**: `value` (Variant, required)
- **Returns**: Boolean — `True` if empty/null/zero-like; `False` otherwise
End If

Set ax = Nothing
%>
```
