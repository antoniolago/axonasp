# Repeat a String

## Overview

Returns a new string formed by repeating the source string a specified number of times.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxRepeat(str, count)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | The string to repeat. |
| count | Integer | Yes | The number of times to repeat `str`. Negative values are treated as `0`. |

## Return Value

- **String**: Returns `str` concatenated `count` times.
- **String**: Returns an empty string when `count` is `0` or negative, or when fewer than two arguments are provided.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxRepeat("AB", 4)
' Output: ABABABAB

Response.Write ax.AxRepeat("-", 20)
' Output: --------------------

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxRepeat`
- **Arguments**: `str As String, count As Integer`
- **Returns**: `String` (repeated string)
