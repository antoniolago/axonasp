# Parse JSON Text

## Overview

Parses JSON text and returns the corresponding native G3Pix AxonASP value.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3JSON")`.

## Syntax

```asp
result = json.Parse(jsonText)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **jsonText** | String | Yes | JSON payload to parse. |

## Return Value

- **Scripting.Dictionary**: Returned when the JSON root is an object.
- **Array**: Returned when the JSON root is an array.
- **String / Integer / Double / Boolean / Null**: Returned when the JSON root is a primitive.
- **Empty**: Returned when the argument is missing, empty, or invalid JSON.

## Remarks

- Method names are case-insensitive.
- Object and array values are converted recursively.

## Example

```asp
<%
Option Explicit
Dim json, data
Set json = Server.CreateObject("G3JSON")

Set data = json.Parse("{""name"": ""AxonASP"", ""enabled"": true}")
If IsObject(data) Then
    Response.Write data("name")
End If

Set data = Nothing
Set json = Nothing
%>
```

## API Reference

- **Object**: `G3JSON`
- **Method**: `Parse`
- **Arguments**: `jsonText` (String, required)
- **Returns**: Dictionary, Array, scalar primitive, Null, or Empty on failure
