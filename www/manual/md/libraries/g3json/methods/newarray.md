# Create a New JSON Array Container

## Overview

Creates an empty VBScript array for JSON composition.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3JSON")`.

## Syntax

```asp
arr = json.NewArray()
```

## Parameters

None.

## Return Value

- **Array**: Empty VBScript array.

## Remarks

- Use this method to build array payloads before calling `Stringify`.

## Example

```asp
<%
Option Explicit
Dim json, arr
Set json = Server.CreateObject("G3JSON")

arr = json.NewArray()
Response.Write IsArray(arr)

Set json = Nothing
%>
```

## API Reference

- **Object**: `G3JSON`
- **Method**: `NewArray`
- **Arguments**: none
- **Returns**: Array — empty VBScript array
