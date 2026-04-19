# Global Property

## Overview

Gets or sets whether the regular expression operates in global mode, applying to all matches in the input string rather than only the first.

## Syntax

```asp
re.Global = True
value = re.Global
```

## Return Value

Returns a **Boolean** indicating the current global mode setting. Returns **False** by default when the object is first created.

## How It Works

Setting `Global` to True or False updates the internal flag only. **The pattern is not recompiled** when `Global` changes. The flag is read at the moment `Execute` or `Replace` is called:

- `Execute` with `Global = True` calls `FindAllStringSubmatchIndex` to collect all non-overlapping matches.
- `Execute` with `Global = False` calls `FindStringSubmatchIndex` and returns at most one match.
- `Replace` with `Global = True` replaces all matches; `Global = False` replaces only the first.
- `Test` is unaffected by `Global`.

## Remarks

- The default value is **False**.
- Changing `Global` does not trigger pattern recompilation. Only `Pattern`, `IgnoreCase`, and `MultiLine` trigger recompilation.

## Code Example

```asp
<%
Option Explicit
Dim re, result
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "\\d+"
re.Global = True

result = re.Replace("Room 101, Floor 3, Unit 42", "#")
Response.Write result
' Output: Room #, Floor #, Unit #

Set re = Nothing
%>
```
