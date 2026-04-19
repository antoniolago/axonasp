# Execute Method

## Overview

Applies the compiled regular expression pattern to an input string and returns a MatchesCollection object containing all matches found.

## Syntax

```asp
Set matches = re.Execute(string)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| string | String | Yes | The text to search for pattern matches. |

## Return Value

Returns a **MatchesCollection** object. Use `Set` for assignment. When no matches are found, the returned collection is empty (`Count` equals 0). Never returns Empty or Nothing.

- When `Global` is **False** (default), the collection contains at most one Match object for the first match found.
- When `Global` is **True**, the collection contains one Match object per non-overlapping match, in order of occurrence.

Each Match object in the collection exposes:
- **Value** (String) — the matched text
- **FirstIndex** (Integer) — the 0-based start position in the input string
- **Length** (Integer) — the character count of the matched text
- **SubMatches** (SubMatches) — a collection of captured group strings

## How It Works

The runtime calls `FindStringSubmatchIndex` (first-only mode) or `FindAllStringSubmatchIndex` (global mode) on the compiled Go `*regexp.Regexp`. If the pattern has not yet been compiled (because `Pattern` was never set or was set to an empty string), the method recompiles before executing. If the pattern is still absent, an empty MatchesCollection is returned immediately.

Submatches are extracted from the index pairs starting at position 2 in the index slice. If a capturing group did not participate in the match, its SubMatches slot contains an empty String.

## Remarks

- If `Pattern` is empty, the method returns an empty MatchesCollection without raising an error.
- If `Pattern` is syntactically invalid, VBScript error 5017 is raised and an empty MatchesCollection is returned.
- Accessing a MatchesCollection or Match object requires `Set` for assignment.
- `matches.Item(0)` and `matches(0)` are equivalent; `Item` is the default dispatch member.

## Code Example

```asp
<%
Option Explicit
Dim re, matches, m, i
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "([A-Za-z]+)@([A-Za-z]+\\.com)"
re.Global = True
re.IgnoreCase = True

Set matches = re.Execute("Contact us at info@example.com or sales@company.com")
For i = 0 To matches.Count - 1
    Set m = matches.Item(i)
    Response.Write "Email: " & m.Value & "<br>"
    Response.Write "User: " & m.SubMatches(0) & "<br>"
    Response.Write "Domain: " & m.SubMatches(1) & "<br>"
    Set m = Nothing
Next
Set matches = Nothing
Set re = Nothing
%>
```
