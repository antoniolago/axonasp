# Serialize Data to JSON Text

## Overview

Serializes a native G3Pix AxonASP value into JSON text.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3JSON")`.

## Syntax

```asp
jsonText = json.Stringify(value)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **value** | Any | Yes | Dictionary, array, scalar value, Null, or Empty. |

## Return Value

- **String**: Serialized JSON text when serialization succeeds.
- **String**: Empty string when the argument is missing.
- **String**: Empty string when serialization fails.

## Remarks

- Dictionary keys become JSON object properties.
- Array values preserve source order.

## Example

```asp
<%
Option Explicit
Dim json, obj, payload
Set json = Server.CreateObject("G3JSON")

Set obj = json.NewObject()
obj.Add "name", "G3Pix AxonASP"
obj.Add "ok", True

payload = json.Stringify(obj)
Response.Write payload

Set obj = Nothing
Set json = Nothing
%>
```

## API Reference

- **Object**: `G3JSON`
- **Method**: `Stringify`
- **Arguments**: `value` (Any, required)
- **Returns**: String — serialized JSON, or empty string on failure
