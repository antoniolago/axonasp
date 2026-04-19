# Check If a Value Is a Floating-Point Number

## Overview

Determines whether the VM internal type of a value is `VTDouble` (Double precision floating-point).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxIsFloat(value)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **value** | Variant | Yes | The value to inspect. |

## Return Value

- **Boolean `True`**: The value's VM internal type is `VTDouble`.
- **Boolean `False`**: The value is not a `VTDouble`, or no argument was supplied.

## Remarks

- This method checks the VM's internal type tag, not the VBScript `VarType`.
- Use `AxIsInt` to check for Integer values.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, a, b
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

a = 3.14
b = 3

Response.Write ax.AxIsFloat(a) & "<br>"  ' True
Response.Write ax.AxIsFloat(b) & "<br>"  ' False

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIsFloat`
- **Arguments**: `value` (Variant, required)
- **Returns**: Boolean — `True` if VM type is `VTDouble`; `False` otherwise
