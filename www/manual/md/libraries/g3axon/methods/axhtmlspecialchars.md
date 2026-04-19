# Escape HTML Special Characters

## Overview

Escapes the HTML special characters in a string to their corresponding HTML entities, preventing browsers from interpreting them as markup.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxHtmlSpecialChars(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The string to escape. |

## Return Value

- **String**: The input string with `&`, `<`, `>`, and `"` replaced by their HTML entity equivalents.
- **String (empty)**: Returned when no argument is supplied.

## Remarks

- Characters replaced: `&` → `&amp;`, `<` → `&lt;`, `>` → `&gt;`, `"` → `&#34;`.
- Use this method when outputting user-supplied data into HTML to prevent cross-site scripting (XSS) attacks.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, safe
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

safe = ax.AxHtmlSpecialChars("<script>alert('xss')</script>")
Response.Write safe
' Output: &lt;script&gt;alert(&#34;xss&#34;)&lt;/script&gt;

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxHtmlSpecialChars`
- **Arguments**: `str` (String, required)
- **Returns**: String — HTML-entity-escaped version of the input