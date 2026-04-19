# Get the Current Error Message

## Overview

Returns the latest error text recorded by the G3DB object.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
errText = db.GetError()
```

## Parameters

None.

## Return Value

- **String**: Latest recorded error message.
- **String**: Empty string when no error is currently stored.

## Remarks

- Alias: `GetLastError`.
- Returns the same value exposed by the `LastError` property.

## Example

```asp
<%
Option Explicit
Dim db
Set db = Server.CreateObject("G3DB")

If Not db.Open("mysql", "bad") Then
    Response.Write db.GetError()
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `GetError`
- **Arguments**: none
- **Returns**: String — current error message (or empty string)
