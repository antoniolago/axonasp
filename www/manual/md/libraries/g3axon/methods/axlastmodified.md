# Get the Last Modified Timestamp of the Current Page

## Overview

Returns the Unix timestamp of the last modification time of the currently executing ASP script file.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxLastModified()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **Integer**: Unix timestamp of the current file's last modification time.
- **Integer `0`**: Returned when the modification time cannot be determined (for example, when the script path is unavailable).

## Remarks

- The method resolves the current script path using `Server.MapPath("")` internally.
- Use the return value with `AxDate` to format it as a human-readable string.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, ts
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

ts = ax.AxLastModified()

If ts > 0 Then
    Response.Write "Page last modified: " & ax.AxDate("Y-m-d H:i:s", ts)
Else
    Response.Write "Modification time unavailable."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxLastModified`
- **Arguments**: None
- **Returns**: Integer — Unix timestamp of the script's last modification, or `0` on failure
