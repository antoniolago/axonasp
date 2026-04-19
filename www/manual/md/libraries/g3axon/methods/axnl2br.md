# Convert Newlines to HTML Line Breaks

## Overview

Replaces all newline sequences in a string with `<br>` HTML tags.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxNl2br(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | The source string containing newlines to replace. |

## Return Value

- **String**: Returns a copy of `str` with all `CRLF` (`\r\n`), `LF` (`\n`), and `CR` (`\r`) sequences replaced by `<br>`.
- **String**: Returns an empty string when no argument is provided.

## Remarks

- `CRLF` sequences are replaced first before individual `LF` and `CR` characters.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, text
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

text = "Line 1" & vbCrLf & "Line 2" & vbCrLf & "Line 3"
Response.Write ax.AxNl2br(text)
' Output: Line 1<br>Line 2<br>Line 3

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxNl2br`
- **Arguments**: `str As String`
- **Returns**: `String` (string with newlines replaced by `<br>`)
