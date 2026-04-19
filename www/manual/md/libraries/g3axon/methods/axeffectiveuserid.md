# Get the Effective User ID

## Overview

Returns the effective user ID (`euid`) of the AxonASP process.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxEffectiveUserId()
```

## Parameters

This method does not require parameters.

## Return Value

- **Integer**: Returns the numeric effective user ID on Unix-like systems.
- **Integer**: Returns `-1` on Windows, where the effective user ID concept does not apply.

## Remarks

- On Unix-like systems, a return value of `0` indicates the process is running as root.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

If ax.AxEffectiveUserId() = 0 Then
    Response.Write "Running as root/superuser"
ElseIf ax.AxEffectiveUserId() = -1 Then
    Response.Write "Windows: effective UID not applicable"
Else
    Response.Write "Effective UID: " & ax.AxEffectiveUserId()
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxEffectiveUserId`
- **Arguments**: none
- **Returns**: `Integer` (euid on Unix, `-1` on Windows)
