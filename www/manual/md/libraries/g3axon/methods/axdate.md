# Format a Date and Time String

## Overview

Formats a Unix timestamp (or the current server time if omitted) into a readable string using PHP-compatible format tokens.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxDate(format [, timestamp])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **format** | String | Yes | A format string composed of PHP-like tokens. |
| **timestamp** | Integer | No | A Unix timestamp (seconds since 1970-01-01 UTC). Defaults to the current server time when omitted. |

**Supported format tokens:**

| Token | Description | Example |
|---|---|---|
| `Y` | 4-digit year | `2025` |
| `m` | Month with leading zero | `01`–`12` |
| `d` | Day of month with leading zero | `01`–`31` |
| `H` | Hour in 24-hour format with leading zero | `00`–`23` |
| `i` | Minutes with leading zero | `00`–`59` |
| `s` | Seconds with leading zero | `00`–`59` |
| `a` | Lowercase ante/post meridiem | `am` / `pm` |
| `A` | Uppercase ante/post meridiem | `AM` / `PM` |
| `F` | Full month name | `January` |
| `M` | Abbreviated month name | `Jan` |
| `l` | Full weekday name | `Monday` |
| `D` | Abbreviated weekday name | `Mon` |
| `N` | ISO-8601 day of the week (1=Monday, 7=Sunday) | `1`–`7` |
| `j` | Day of month without leading zero | `1`–`31` |
| `n` | Month without leading zero | `1`–`12` |
| `G` | Hour in 24-hour format without leading zero | `0`–`23` |
| `U` | Unix timestamp | Integer |

## Return Value

- **String**: The input format string with all recognized tokens replaced by their corresponding date/time values.

## Remarks

- Month and weekday names use the locale configured for the AxonASP VM.
- Unrecognized characters in the format string are passed through unchanged.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxDate("Y-m-d H:i:s") & "<br>"
' Output (example): 2025-06-15 14:30:00

Response.Write ax.AxDate("l, F j, Y", 1735689600) & "<br>"
' Output (example): Wednesday, January 1, 2025

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxDate`
- **Arguments**: `format` (String, required), `timestamp` (Integer, optional)
- **Returns**: String — formatted date/time string
