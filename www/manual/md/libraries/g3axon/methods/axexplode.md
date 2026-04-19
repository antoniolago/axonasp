# Split a String into an Array

## Overview

Splits a string by a specified delimiter and returns a zero-based VBArray of the resulting substrings.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
arr = obj.AxExplode(delimiter, str [, limit])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| delimiter | String | Yes | The string used to split `str`. When empty, each character becomes a separate element. |
| str | String | Yes | The string to split. |
| limit | Integer | Optional | Maximum number of elements to return. When specified, the last element contains the remainder of the string. |

## Return Value

- **Array**: Returns a zero-based VBArray of String elements.
- **Array**: Returns an empty array when fewer than two arguments are provided.

## Remarks

- When `delimiter` is empty, `str` is split into individual characters.
- When `limit` is greater than the actual number of parts, it has no effect.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, parts, i
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

parts = ax.AxExplode(",", "apple,banana,cherry")
For i = 0 To UBound(parts)
    Response.Write parts(i) & "<br>"
Next
' Output:
' apple
' banana
' cherry

' Limit to 2 parts
parts = ax.AxExplode(",", "a,b,c,d", 2)
Response.Write parts(0) & " / " & parts(1)
' Output: a / b

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxExplode`
- **Arguments**: `delimiter As String, str As String [, limit As Integer]`
- **Returns**: `Array` (zero-based VBArray of String elements)
