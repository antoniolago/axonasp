# Replace All Occurrences of a Substring

## Overview

Replaces every occurrence of a search string within a source string and returns the modified result.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxStringReplace(search, replacement, subject)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| search | String | Yes | The substring to find in `subject`. |
| replacement | String | Yes | The string to substitute for each occurrence of `search`. |
| subject | String | Yes | The source string to search within. |

## Return Value

- **String**: Returns a copy of `subject` with all occurrences of `search` replaced by `replacement`.
- **String**: Returns an empty string when fewer than three arguments are provided.

## Remarks

- The replacement is case-sensitive.
- All non-overlapping occurrences are replaced in a single pass.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, result
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

result = ax.AxStringReplace("world", "AxonASP", "Hello world")
Response.Write result
' Output: Hello AxonASP

' Remove a character
result = ax.AxStringReplace("-", "", "2025-04-18")
Response.Write result
' Output: 20250418

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxStringReplace`
- **Arguments**: `search As String, replacement As String, subject As String`
- **Returns**: `String` (modified copy of `subject`)
