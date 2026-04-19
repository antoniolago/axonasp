# Write HTML-Escaped Text to the Response

## Overview

Writes a string to the current HTTP response after escaping all HTML special characters. This is a safe alternative to `Response.Write` when outputting user-supplied or untrusted data.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
ax.AxW(text)
```

This method is also accessible as `ax.document.write(text)` and `ax.documentwrite(text)` for compatibility.

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **text** | String | Yes | The text to write to the response. HTML special characters are escaped before output. |

## Return Value

- **Empty**: This method does not return a value.

## Remarks

- Characters escaped: `&` → `&amp;`, `<` → `&lt;`, `>` → `&gt;`, `"` → `&#34;`.
- Use `Response.Write` when you intentionally need to output raw HTML markup.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, userInput
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

userInput = "<script>alert('xss')</script>"

' Renders safely as literal text — no script executes.
ax.AxW userInput

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxW` (also: `document.write`, `documentwrite`)
- **Arguments**: `text` (String, required)
- **Returns**: Empty
