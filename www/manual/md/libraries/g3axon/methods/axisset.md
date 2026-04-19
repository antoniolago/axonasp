# Check If a Value Is Set

## Overview

Determines whether a value has been initialized and is neither `Empty` nor `Null`.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxIsSet(value)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **value** | Variant | Yes | The value to inspect. |

## Return Value

- **Boolean `True`**: The value is initialized and is not `Empty` or `Null`.
- **Boolean `False`**: The value is `Empty` or `Null`.

## Remarks

- This method is the inverse of the VBScript `IsEmpty` and `IsNull` checks combined.
- Unlike `AxEmpty`, this method does not consider zero (`0`), empty string (`""`), or `False` as unset. Only `Empty` and `Null` return `False`.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, val
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' val is uninitialized (Empty)
Response.Write ax.AxIsSet(val) & "<br>"   ' False

val = 0
Response.Write ax.AxIsSet(val) & "<br>"   ' True (0 is a set value)

val = "hello"
Response.Write ax.AxIsSet(val) & "<br>"   ' True

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIsSet`
- **Arguments**: `value` (Variant, required)
- **Returns**: Boolean — `True` if value is not `Empty` or `Null`; `False` otherwise
