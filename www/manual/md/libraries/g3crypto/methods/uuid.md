# Generate a UUID v4

## Overview

Generates one RFC 4122 version 4 UUID string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
result = crypto.UUID()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **String**: UUID string in the `8-4-4-4-12` format, using lowercase hexadecimal characters.
- **String (empty)**: Returned when cryptographic random generation fails.

## Remarks

- Use this method for unique identifiers where randomness and uniqueness are required.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim crypto, id
Set crypto = Server.CreateObject("G3CRYPTO")

id = crypto.UUID()
Response.Write id

Set crypto = Nothing
%>
```

## API Reference

- **Object**: `G3CRYPTO`
- **Method**: `UUID`
- **Arguments**: None
- **Returns**: String — UUID v4 text, or empty string on random-source failure
