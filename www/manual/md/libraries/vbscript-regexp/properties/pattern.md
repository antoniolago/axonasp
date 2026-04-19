# Pattern Property

## Overview

Gets or sets the regular expression pattern string used for matching, replacement, and testing operations.

## Syntax

```asp
re.Pattern = "expression"
value = re.Pattern
```

## Return Value

Returns a **String** containing the current pattern. Returns an empty String when no pattern has been assigned.

## How It Works

Assigning a value to `Pattern` immediately compiles the expression against the current `IgnoreCase` and `MultiLine` flags. If the pattern is syntactically invalid, VBScript error 5017 (Regular expression syntax error) is raised and the compiled expression is cleared, causing subsequent `Execute`, `Test`, and `Replace` calls to fail gracefully rather than match unpredictably.

Setting `Pattern` to an empty String clears the compiled expression without raising an error.

## Remarks

- The pattern uses RE2 syntax. Lookahead (`(?=...)`, `(?!...)`), lookbehind (`(?<=...)`, `(?<!...)`), and backreferences (`\\1`) are **not supported** and will raise error 5017 when assigned.
- Character classes, quantifiers, anchors, and named groups (`(?P<name>...)`) are fully supported.
- Changing `IgnoreCase` or `MultiLine` after setting `Pattern` recompiles the expression automatically.

## Code Example

```asp
<%
Option Explicit
Dim re
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "\\b[A-Z]{2,}\\b"
re.Global = True

Response.Write re.Pattern
' Output: \b[A-Z]{2,}\b

Set re = Nothing
%>
```
