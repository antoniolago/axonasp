# Strip HTML and XML Tags from a String

## Overview

Removes all HTML and XML tags from a string, returning only the plain text content.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxStripTags(str)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **str** | String | Yes | The string from which to remove HTML and XML tags. |

## Return Value

- **String**: The input string with all content between `<` and `>` removed.
- **String (empty)**: Returned when no argument is supplied.

## Remarks

- Tags are identified and removed using a regular expression that matches any sequence from `<` to `>`.
- Comments (`<!-- ... -->`) and processing instructions (`<? ... ?>`) are also removed.
- This method does not decode HTML entities. Use `AxHtmlSpecialChars` to escape output, not sanitize HTML.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, html, plain
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

html = "<p>Hello <b>AxonASP</b>!</p><!-- comment -->"
plain = ax.AxStripTags(html)
Response.Write plain
' Output: Hello AxonASP!

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxStripTags`
- **Arguments**: `str` (String, required)
- **Returns**: String — input with all HTML/XML tags removed
