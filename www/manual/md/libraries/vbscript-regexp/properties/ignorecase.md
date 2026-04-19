# IgnoreCase Property

## Overview

Gets or sets whether the regular expression matching is case-insensitive.

## Syntax

```asp
re.IgnoreCase = True
value = re.IgnoreCase
```

## Return Value

Returns a **Boolean** indicating the current case-sensitivity setting. Returns **False** by default when the object is first created.

## How It Works

Setting `IgnoreCase` to True prepends the `(?i)` flag to the compiled pattern. Setting it to False removes that flag. After any change to this property, the pattern is recompiled immediately using the current `Pattern` and `MultiLine` values. If `Pattern` is empty, no compilation is triggered.

## Remarks

- The default value is **False** (case-sensitive matching).
- Changing `IgnoreCase` after `Pattern` has been set recompiles the expression in-place.
- `IgnoreCase` affects `Execute`, `Test`, and `Replace` equally.

## Code Example

```asp
<%
Option Explicit
Dim re
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "hello"
re.IgnoreCase = True

If re.Test("Say HELLO world") Then
    Response.Write "Match found (case-insensitive)."
End If

Set re = Nothing
%>
```
