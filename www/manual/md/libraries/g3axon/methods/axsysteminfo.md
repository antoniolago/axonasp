# Get System Information

## Overview

Retrieves operating system and runtime environment details for the current server process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxSystemInfo([mode])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **mode** | String | No | A single character selecting the category of information to return. Omit or pass any unrecognized value to receive all categories combined. |

**mode values:**

| Value | Returns |
|---|---|
| `"s"` | Operating system name (e.g., `"windows"`, `"linux"`, `"darwin"`). |
| `"n"` | Hostname of the machine. |
| `"v"` | Go runtime version (e.g., `"go1.22.0"`). |
| `"m"` | Machine architecture (e.g., `"amd64"`, `"arm64"`). |
| `"a"` or omitted | All categories combined in a single string. |

## Return Value

- **String**: The requested system information. Returns all categories combined when `mode` is omitted or unrecognized.

## Remarks

- Any unrecognized or empty mode value defaults to `"a"` (all information).
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

Response.Write "OS: " & ax.AxSystemInfo("s") & "<br>"
Response.Write "Hostname: " & ax.AxSystemInfo("n") & "<br>"
Response.Write "Architecture: " & ax.AxSystemInfo("m") & "<br>"
Response.Write "Go version: " & ax.AxSystemInfo("v") & "<br>"
Response.Write "Full info: " & ax.AxSystemInfo() & "<br>"

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxSystemInfo`
- **Arguments**: `mode` (String, optional) — `"s"`, `"n"`, `"v"`, `"m"`, or `"a"`
- **Returns**: String — system information for the selected category
