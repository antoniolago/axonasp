# Check If a String Contains Only Alphanumeric Characters

## Overview

Determines whether every character in a string is an ASCII alphanumeric character (a–z, A–Z, or 0–9).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxCtypeAlnum(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The string to test. |

## Return Value

- **Boolean `True`**: All characters in the string are ASCII alphanumeric.
- **Boolean `False`**: The string contains non-alphanumeric characters, the string is empty, or no argument was supplied.

## Remarks

- Only ASCII letters `A`–`Z`, `a`–`z`, and digits `0`–`9` are considered alphanumeric. Spaces, punctuation, and Unicode characters return `False`.
- An empty string always returns `False`.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxCtypeAlnum("AxonASP2026") & "<br>"  ' True
Response.Write ax.AxCtypeAlnum("Axon-ASP") & "<br>"    ' False (hyphen)
Response.Write ax.AxCtypeAlnum("") & "<br>"            ' False (empty)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxCtypeAlnum`
- **Arguments**: `str` (String, required)
- **Returns**: Boolean — `True` if all characters are ASCII alphanumeric; `False` otherwise
