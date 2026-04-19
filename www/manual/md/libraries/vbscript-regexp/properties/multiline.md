# MultiLine Property

## Overview

Gets or sets whether the `^` and `$` anchors match at the start and end of each line within the input string, rather than only at the very start and end of the entire string.

## Syntax

```asp
re.MultiLine = True
value = re.MultiLine
```

## Return Value

Returns a **Boolean** indicating the current multi-line mode setting. Returns **False** by default when the object is first created.

## How It Works

Setting `MultiLine` to True prepends the `(?m)` flag to the compiled pattern. Setting it to False removes that flag. After any change to this property, the pattern is recompiled immediately using the current `Pattern` and `IgnoreCase` values.

With `MultiLine = True`:
- `^` matches at position 0 and immediately after any `\n` character.
- `$` matches immediately before any `\n` character and at the end of the string.

## Remarks

- The default value is **False**.
- Changing `MultiLine` after `Pattern` has been set triggers immediate recompilation.
- `MultiLine` applies equally to `Execute`, `Test`, and `Replace`.
- Dot (`.`) does **not** match newlines regardless of this setting. Use `[\\s\\S]` to match any character including newlines.

## Code Example

```asp
<%
Option Explicit
Dim re, matches
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "^Item"
re.Global = True
re.MultiLine = True

Dim text
text = "Item A" & Chr(10) & "Item B" & Chr(10) & "Other C"

Set matches = re.Execute(text)
Response.Write "Lines starting with 'Item': " & matches.Count
' Output: Lines starting with 'Item': 2

Set matches = Nothing
Set re = Nothing
%>
```
