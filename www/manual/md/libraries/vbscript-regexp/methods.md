# Methods

## Overview

This page lists all methods exposed by the VBScript.RegExp object.

## RegExp Methods

| Method | Returns | Description |
|---|---|---|
| Execute(string) | MatchesCollection | Applies the compiled pattern to the input string and returns a MatchesCollection containing all matches found. When `Global` is False, at most one match is returned. |
| Replace(string, replacement) | String | Replaces matches of the pattern within `string` with the `replacement` text and returns the resulting String. When `Global` is False, only the first match is replaced. |
| Test(string) | Boolean | Returns True if the pattern matches anywhere in the input string; returns False if there is no match or the pattern has not been compiled. |

## MatchesCollection Methods

A MatchesCollection object is returned by `Execute`. It is read-only.

| Method | Returns | Description |
|---|---|---|
| Item(index) | Match | Returns the Match object at the specified 0-based index. Returns Empty if the index is out of range. |
| Count() | Integer | Returns the total number of Match objects in the collection. |

## Match Methods

A Match object is obtained from a MatchesCollection via `Item`.

| Method | Returns | Description |
|---|---|---|
| SubMatches([index]) | SubMatches or String | With no argument, returns the SubMatches collection for this match. With an integer argument, returns the String value of the captured group at that 0-based index. Returns Empty if the index is out of range. |

## SubMatches Methods

| Method | Returns | Description |
|---|---|---|
| Item(index) | SubMatchValue | Returns the SubMatchValue object for the captured group at the specified 0-based index. Returns Empty if the index is out of range. |
| Count() | Integer | Returns the number of captured groups in this SubMatches collection. |

## Remarks

- A MatchesCollection, Match, or SubMatches object is a native handle. Use `Set` for assignment.
- The `Item` method is the default dispatch member; `matches(0)` and `matches.Item(0)` are equivalent.
