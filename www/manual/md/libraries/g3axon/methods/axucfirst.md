# Uppercase the First Character

## Overview

Returns a copy of the input string with the first Unicode character converted to uppercase.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxUcfirst(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | The source string. |

## Return Value

- **String**: Returns `str` with the first character converted to uppercase and remaining characters unchanged.
- **String**: Returns an empty string when `str` is empty or no argument is provided.

## Remarks

- Method names are case-insensitive in VBScript dispatch.
- Only the first Unicode character is uppercased; all other characters are left as-is.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write ax.AxUcfirst("hello world")
' Output: Hello world

Response.Write ax.AxUcfirst("axonASP")
' Output: AxonASP

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxUcfirst`
- **Arguments**: `str As String`
- **Returns**: `String` (string with uppercased first character)
