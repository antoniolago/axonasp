# Properties

## Overview

This page lists all properties exposed by the VBScript.RegExp object and its sub-objects.

## RegExp Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Global | Read/Write | Boolean | When True, `Execute` finds all non-overlapping matches and `Replace` replaces all occurrences. When False (default), only the first match is processed. Changing this property does not recompile the pattern. |
| IgnoreCase | Read/Write | Boolean | When True, the compiled pattern ignores letter case during matching. When False (default), matching is case-sensitive. Changing this property recompiles the pattern immediately. |
| MultiLine | Read/Write | Boolean | When True, the `^` and `$` anchors match at the start and end of each line within the input string. When False (default), they match only at the start and end of the entire string. Changing this property recompiles the pattern. |
| Pattern | Read/Write | String | The regular expression pattern string. Setting this property compiles the expression immediately. If the pattern is syntactically invalid, VBScript error 5017 is raised and the compiled expression is cleared. Returns an empty String when no pattern has been set. |

## Match Properties

A Match object is obtained from a MatchesCollection via `Item(index)` after calling `Execute`.

| Property | Access | Type | Description |
|---|---|---|---|
| FirstIndex | Read | Integer | The 0-based character position in the input string where the match begins. |
| Length | Read | Integer | The number of characters in the matched text. |
| SubMatches | Read | SubMatches | The SubMatches collection containing the text captured by each parenthesized group in the pattern. |
| Value | Read | String | The complete text of the match. This is the default property; reading a Match object directly returns this value. |

## MatchesCollection Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Count | Read | Integer | The total number of Match objects in the collection. Also accessible as `Length`. |

## SubMatches Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Count | Read | Integer | The number of captured groups in the SubMatches collection. |

## SubMatchValue Properties

A SubMatchValue object is returned by `SubMatches.Item(index)`.

| Property | Access | Type | Description |
|---|---|---|---|
| Length | Read | Integer | The number of characters in the captured group text. |
| Value | Read | String | The text captured by the group. This is the default property. |
