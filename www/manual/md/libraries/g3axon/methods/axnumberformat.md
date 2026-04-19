# Format a Number with Grouping and Decimal Options

## Overview

Formats a numeric value with configurable decimal places, decimal separator, and thousands separator.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxNumberFormat(number [, decimals [, decPoint [, thousandsSep]]])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| number | Double | Yes | The numeric value to format. |
| decimals | Integer | Optional | The number of decimal places to include. Defaults to `2`. |
| decPoint | String | Optional | The decimal separator character. Defaults to `"."`. |
| thousandsSep | String | Optional | The thousands grouping separator. Defaults to `","`. Pass an empty string to disable grouping. |

## Return Value

- **String**: Returns the formatted number as a string.
- **String**: Returns an empty string when no argument is provided.

## Remarks

- Modeled after the PHP `number_format` function behavior.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' US format: 1,234,567.89
Response.Write ax.AxNumberFormat(1234567.891, 2)

' European format: 1.234.567,89
Response.Write ax.AxNumberFormat(1234567.891, 2, ",", ".")

' No decimal, no grouping
Response.Write ax.AxNumberFormat(9876.5, 0, ".", "")
' Output: 9877

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxNumberFormat`
- **Arguments**: `number As Double [, decimals As Integer [, decPoint As String [, thousandsSep As String]]]`
- **Returns**: `String` (formatted number string)
