# Generate a GUID

## Overview

Generates a cryptographically secure version 4 GUID (Globally Unique Identifier) string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxGenerateGuid()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **String**: A 36-character RFC 4122 version 4 GUID in the form `xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx`, where `x` is a random lowercase hexadecimal digit and `y` is one of `8`, `9`, `a`, or `b`.

## Remarks

- The GUID is generated using a cryptographically secure random number generator.
- Each call produces a statistically unique value. Collisions are possible but astronomically unlikely.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, guid
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

guid = ax.AxGenerateGuid()
Response.Write guid
' Output example: f47ac10b-58cc-4372-a567-0e02b2c3d479

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxGenerateGuid`
- **Arguments**: None
- **Returns**: String — 36-character RFC 4122 v4 GUID
