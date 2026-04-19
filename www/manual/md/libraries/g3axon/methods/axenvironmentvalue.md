# Get an Environment Variable Value

## Overview

Retrieves the value of a specific environment variable from the process, with an optional default fallback.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxEnvironmentValue(name [, default])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| name | String | Yes | The name of the environment variable to look up. |
| default | Variant | Optional | The value to return when the variable is not found. Defaults to an empty string. |

## Return Value

- **String**: Returns the value of the environment variable when it exists.
- **Variant**: Returns `default` when the variable is not found and a default was provided.
- **String**: Returns an empty string when the variable is not found and no default was provided.

## Remarks

- On Windows, lookup is case-insensitive. On Unix-like systems, lookup is case-sensitive.
- Unlike `AxGetEnv`, this method lets you specify a fallback value in the same call.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, port
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

port = ax.AxEnvironmentValue("APP_PORT", "8080")
Response.Write "Port: " & port

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxEnvironmentValue`
- **Arguments**: `name As String [, default As Variant]`
- **Returns**: `String` (variable value or default)
