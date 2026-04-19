# Join Array Elements into a String

## Overview

Joins all elements of a VBArray into a single string, separated by the specified glue string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxImplode(glue, inputArray)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| glue | String | Yes | The string placed between each element of `inputArray`. |
| inputArray | Array | Yes | The zero-based VBArray whose elements are joined. |

## Return Value

- **String**: Returns a single string with each array element separated by `glue`.
- **String**: Returns an empty string when `inputArray` is not a valid array or fewer than two arguments are provided.

## Remarks

- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, fruits, result
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

fruits = Array("apple", "banana", "cherry")
result = ax.AxImplode(", ", fruits)
Response.Write result
' Output: apple, banana, cherry

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxImplode`
- **Arguments**: `glue As String, inputArray As Array`
- **Returns**: `String` (joined string)
