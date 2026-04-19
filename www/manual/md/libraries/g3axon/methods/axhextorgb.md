# Convert a Hexadecimal Color Code to RGB

## Overview

Converts an HTML hexadecimal color string to a CSS `rgb()` function string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxHexToRgb(hex)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **hex** | String | Yes | An HTML color string in `#RGB` or `#RRGGBB` format. The leading `#` is required. |

## Return Value

- **String**: A CSS color string in `rgb(R,G,B)` format (e.g., `"rgb(0,128,255)"`).
- **String `"rgb(0,0,0)"`**: Returned when the input is empty, missing the `#` prefix, or has an invalid format.

## Remarks

- Both 3-digit (`#RGB`) and 6-digit (`#RRGGBB`) formats are accepted.
- The 3-digit form is expanded by doubling each digit (e.g., `#F80` → `#FF8800`).
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, rgb
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

rgb = ax.AxHexToRgb("#0080FF")
Response.Write rgb
' Output: rgb(0,128,255)

rgb = ax.AxHexToRgb("#F80")
Response.Write "<br>" & rgb
' Output: rgb(255,136,0)

rgb = ax.AxHexToRgb("invalid")
Response.Write "<br>" & rgb
' Output: rgb(0,0,0)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxHexToRgb`
- **Arguments**: `hex` (String, required)
- **Returns**: String — `rgb(R,G,B)` form, or `rgb(0,0,0)` on invalid input