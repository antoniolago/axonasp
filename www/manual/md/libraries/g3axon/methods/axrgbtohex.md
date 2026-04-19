# Convert RGB Values to a Hexadecimal Color Code

## Overview

Converts individual red, green, and blue color component values to an uppercase HTML hexadecimal color string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxRgbToHex(r, g, b)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **r** | Integer | Yes | Red component (0–255). Values outside this range are masked with `& 0xFF`. |
| **g** | Integer | Yes | Green component (0–255). Values outside this range are masked with `& 0xFF`. |
| **b** | Integer | Yes | Blue component (0–255). Values outside this range are masked with `& 0xFF`. |

## Return Value

- **String**: An uppercase hexadecimal color string in `#RRGGBB` format (e.g., `"#FF8000"`).
- **String `"#000000"`**: Returned when fewer than three arguments are supplied.

## Remarks

- Each component is masked with `& 0xFF` before formatting, so values outside 0–255 wrap rather than cause an error.
- The hex digits are uppercase (`A`–`F`).
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, hex
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

hex = ax.AxRgbToHex(255, 128, 0)
Response.Write hex
' Output: #FF8000

hex = ax.AxRgbToHex(0, 0, 255)
Response.Write "<br>" & hex
' Output: #0000FF

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxRgbToHex`
- **Arguments**: `r` (Integer, required), `g` (Integer, required), `b` (Integer, required)
- **Returns**: String — uppercase `#RRGGBB` hex color code