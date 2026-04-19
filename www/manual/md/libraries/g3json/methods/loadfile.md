# Load JSON from File

## Overview

Reads a JSON file and parses it into a native G3Pix AxonASP value.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3JSON")`.

## Syntax

```asp
result = json.LoadFile(path)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **path** | String | Yes | Virtual or physical path to a JSON file. |

## Return Value

- **Scripting.Dictionary**: Returned when the JSON root is an object.
- **Array**: Returned when the JSON root is an array.
- **String / Integer / Double / Boolean / Null**: Returned when the JSON root is a primitive.
- **Empty**: Returned when `path` is missing, file read fails, or JSON parsing fails.

## Remarks

- Virtual paths are mapped through the server host when available.
- Parsing behavior matches `Parse`.

## Example

```asp
<%
Option Explicit
Dim json, cfg
Set json = Server.CreateObject("G3JSON")

Set cfg = json.LoadFile("/config/settings.json")
If IsObject(cfg) Then
    Response.Write cfg("appName")
End If

Set cfg = Nothing
Set json = Nothing
%>
```

## API Reference

- **Object**: `G3JSON`
- **Method**: `LoadFile`
- **Arguments**: `path` (String, required)
- **Returns**: Dictionary, Array, scalar primitive, Null, or Empty on failure
