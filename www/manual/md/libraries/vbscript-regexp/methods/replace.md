# Replace Method

## Overview

Replaces pattern matches within an input string with a replacement string and returns the resulting text.

## Syntax

```asp
result = re.Replace(string, replacement)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| string | String | Yes | The source text in which to perform replacements. |
| replacement | String | Yes | The replacement text. Supports substitution tokens (see Remarks). |

## Return Value

Returns a **String** containing the source text after replacements have been applied.

- When `Global` is **False** (default), only the first match is replaced.
- When `Global` is **True**, all non-overlapping matches are replaced.
- If the pattern does not match anywhere in `string`, the original `string` is returned unchanged.
- If fewer than two arguments are supplied, the method returns the first argument as-is, or an empty String if no arguments are given.

## How It Works

The runtime locates match positions using `FindStringSubmatchIndex` or `FindAllStringSubmatchIndex` and rebuilds the string by inserting the processed replacement between each unmatched segment. Before insertion, the replacement string is scanned for substitution tokens and each token is expanded:

| Token | Expanded value |
|---|---|
| `$&` or `$0` | The entire matched text. |
| `$1`, `$2`, ... | The text of captured group 1, 2, ... If the group did not participate in the match, an empty String is substituted. |
| `` $` `` | The text in `string` before the match. |
| `$'` | The text in `string` after the match. |

## Remarks

- If `Pattern` is empty, the original `string` is returned without modification.
- If `Pattern` is syntactically invalid, VBScript error 5017 is raised and the original `string` is returned.
- Replacement tokens are processed case-sensitively. `$1` is never the same as `$01`.
- To include a literal dollar sign in the output, use `$$` is not supported; use a different delimiter or post-process the result.

## Code Example

```asp
<%
Option Explicit
Dim re, result
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "(\\d{4})-(\\d{2})-(\\d{2})"
re.Global = False

' Reformat ISO date to DD/MM/YYYY
result = re.Replace("Event date: 2025-12-31", "$3/$2/$1")
Response.Write result
' Output: Event date: 31/12/2025

Set re = Nothing
%>
```
