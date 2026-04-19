# Use VBScript.RegExp in AxonASP

## Overview

VBScript.RegExp provides regular expression matching, searching, and replacement for Classic ASP scripts. Use it to validate input, extract substrings, and perform pattern-based text transformations.

The object supports the full regular expression syntax accepted by Go's `regexp` package, which follows RE2 semantics. This is compatible with the majority of VBScript regex patterns, with the exception of lookahead and lookbehind assertions and backreferences, which are not supported by RE2.

## Prerequisites

- Set `Pattern` before calling any method. Calling `Execute`, `Test`, or `Replace` without a pattern returns an empty Matches collection, `False`, or the original input string respectively.
- Setting `IgnoreCase` or `MultiLine` after `Pattern` recompiles the internal expression automatically.

## Syntax

```asp
Set re = Server.CreateObject("VBScript.RegExp")
```

## Return Value

Returns a native RegExp object handle. Use `Set` for assignment. Call `Set re = Nothing` when the object is no longer needed.

## How It Works

The AxonASP runtime stores each RegExp instance in an internal map keyed by a dynamic numeric ID. Setting the `Pattern`, `IgnoreCase`, or `MultiLine` property triggers an immediate recompile of the underlying Go `*regexp.Regexp`. If the pattern is syntactically invalid, the runtime raises VBScript error 5017 (Regular expression syntax error) and clears the compiled expression.

The `Execute` method returns a **MatchesCollection** object. Iterating it yields individual **Match** objects, each exposing `Value`, `FirstIndex`, `Length`, and a `SubMatches` collection.

**Replacement token syntax supported by `Replace`:**

| Token | Replaced with |
|---|---|
| `$&` or `$0` | The entire matched text |
| `$1`, `$2`, ... | Captured group 1, 2, ... |
| `` $` `` | Text before the match |
| `$'` | Text after the match |

## Remarks

- All method and property names are case-insensitive.
- When `Global` is False (default), `Execute` returns at most one match and `Replace` replaces only the first occurrence.
- When `Global` is True, `Execute` returns all non-overlapping matches and `Replace` replaces all occurrences.
- `FirstIndex` on a Match object is 0-based, consistent with classic VBScript behavior.
- Lookahead, lookbehind, and backreferences (`\1`, `\2`) are not supported.

## Code Example

```asp
<%
Option Explicit
Dim re, matches, m
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "(\\d+)"
re.Global = True

Set matches = re.Execute("Order 123 and invoice 456")
Dim i
For i = 0 To matches.Count - 1
    Set m = matches.Item(i)
    Response.Write "Found: " & m.Value & " at index " & m.FirstIndex & "<br>"
    Set m = Nothing
Next
Set matches = Nothing
Set re = Nothing
%>
```

