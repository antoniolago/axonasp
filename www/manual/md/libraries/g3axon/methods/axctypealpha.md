# Check If a String Contains Only Alphabetic Characters

## Overview

Determines whether every character in a string is an ASCII alphabetic letter (a–z or A–Z).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxCtypeAlpha(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The string to test. |

## Return Value

- **Boolean `True`**: All characters in the string are ASCII alphabetic letters.
- **Boolean `False`**: The string contains non-alphabetic characters, the string is empty, or no argument was supplied.

## Remarks

- Only ASCII characters `A`–`Z` and `a`–`z` are considered alphabetic. Accented characters and Unicode letters return `False`.
- An empty string always returns `False`.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxCtypeAlpha("AxonASP") & "<br>"   ' True
Response.Write ax.AxCtypeAlpha("Axon2") & "<br>"    ' False (digit)
Response.Write ax.AxCtypeAlpha("") & "<br>"         ' False (empty)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCtypeAlpha`
- **Arguments**: `str` (String, required)
- **Returns**: Boolean — `True` if all characters are ASCII alphabetic; `False` otherwise
