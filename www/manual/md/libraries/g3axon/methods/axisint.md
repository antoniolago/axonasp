# Check If a Value Is an Integer

## Overview

Determines whether the VM internal type of a value is `VTInteger` (Integer).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxIsInt(value)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **value** | Variant | Yes | The value to inspect. |

## Return Value

- **Boolean `True`**: The value's VM internal type is `VTInteger`.
- **Boolean `False`**: The value is not a `VTInteger`, or no argument was supplied.

## Remarks

- This method checks the VM's internal type tag, not the VBScript `VarType`. A value returned from a function that coerces to an integer at the VBScript level may still fail this check if the VM stored it as a different type.
- Use `AxIsFloat` to check for Double precision values.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, a, b
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

a = 100
b = 100.5

Response.Write ax.AxIsInt(a) & "<br>"  ' True
Response.Write ax.AxIsInt(b) & "<br>"  ' False

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxIsInt`
- **Arguments**: `value` (Variant, required)
- **Returns**: Boolean — `True` if VM type is `VTInteger`; `False` otherwise
