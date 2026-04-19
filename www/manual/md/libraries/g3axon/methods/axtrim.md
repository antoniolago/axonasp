# Trim Characters from Both Ends of a String

## Overview

Removes leading and trailing characters from a string. Defaults to stripping standard whitespace.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxTrim(str [, chars])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | The string to trim. |
| chars | String | Optional | A set of characters to strip from both ends. When omitted, the default set `" \t\n\r\v\f"` is used. |

## Return Value

- **String**: Returns `str` with all leading and trailing occurrences of any character in `chars` removed.
- **String**: Returns an empty string when no argument is provided.

## Remarks

- `chars` works as a character set, not as a literal substring — any character in `chars` is trimmed.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxTrim("   Hello World   ")
' Output: Hello World

Response.Write ax.AxTrim("***data***", "*")
' Output: data

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxTrim`
- **Arguments**: `str As String [, chars As String]`
- **Returns**: `String` (trimmed string)