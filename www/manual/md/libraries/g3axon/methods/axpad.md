# Pad a String to a Specified Length

## Overview

Pads a string to a target length using a specified pad character or string. Supports right-padding, left-padding, and center-padding.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxPad(str, length [, padStr [, padType]])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | The source string to pad. |
| length | Integer | Yes | The target total length of the resulting string. When `str` is already this length or longer, `str` is returned unchanged. |
| padStr | String | Optional | The character or string to use for padding. Defaults to a single space. |
| padType | Integer | Optional | Padding direction: `0` = left, `1` = right (default), `2` = both sides (center). |

## Return Value

- **String**: Returns the padded string when `str` is shorter than `length`.
- **String**: Returns `str` unchanged when it is already equal to or longer than `length`.
- **String**: Returns an empty string when fewer than two arguments are provided.

## Remarks

- When `padType` is `2` (both sides), the extra character is appended to the right side.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' Right-pad with spaces (default)
Response.Write "[" & ax.AxPad("Hi", 8) & "]"           ' [Hi      ]

' Left-pad with zeros
Response.Write "[" & ax.AxPad("42", 6, "0", 0) & "]"   ' [000042]

' Center-pad with dashes
Response.Write "[" & ax.AxPad("Go", 8, "-", 2) & "]"   ' [---Go---]

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxPad`
- **Arguments**: `str As String, length As Integer [, padStr As String [, padType As Integer]]`
- **Returns**: `String` (padded string)
