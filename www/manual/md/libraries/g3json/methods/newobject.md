# Create a New JSON Object Container

## Overview

Creates an empty Scripting.Dictionary object for JSON composition.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3JSON")`.

## Syntax

```asp
Set obj = json.NewObject()
```

## Parameters

None.

## Return Value

- **Scripting.Dictionary**: Empty dictionary object.

## Remarks

- Use this method to build object payloads before calling `Stringify`.

## Example

```asp
<%
Option Explicit
Dim json, obj
Set json = Server.CreateObject("G3JSON")

Set obj = json.NewObject()
obj.Add "status", "ok"
Response.Write obj("status")

Set obj = Nothing
Set json = Nothing
%>
```

## API Reference

- **Object**: `G3JSON`
- **Method**: `NewObject`
- **Arguments**: none
- **Returns**: Scripting.Dictionary — empty dictionary object
