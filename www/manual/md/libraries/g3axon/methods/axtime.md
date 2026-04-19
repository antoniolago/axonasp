# Get the Current Unix Timestamp

## Overview

Returns the number of seconds elapsed since 1970-01-01 00:00:00 UTC (Unix epoch).

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxTime()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **Integer**: The current Unix timestamp in seconds.

## Remarks

- The returned value reflects the server's clock in UTC, adjusted for the configured time zone.
- Pass the return value to `AxDate` to format it as a readable date/time string.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, ts
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

ts = ax.AxTime()
Response.Write "Unix timestamp: " & ts & "<br>"
Response.Write "Formatted: " & ax.AxDate("Y-m-d H:i:s", ts)

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxTime`
- **Arguments**: None
- **Returns**: Integer — current Unix timestamp in seconds
