# Test Method

## Overview

Tests whether the compiled regular expression pattern matches anywhere within an input string.

## Syntax

```asp
result = re.Test(string)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| string | String | Yes | The text to test against the pattern. |

## Return Value

Returns **True** if the pattern matches at least one position in the input string. Returns **False** if there is no match, if no argument is supplied, if `Pattern` is empty, or if the pattern failed to compile.

## How It Works

The runtime calls `MatchString` on the compiled Go `*regexp.Regexp`. If the pattern has not yet been compiled, the runtime attempts to compile it first. If compilation fails, `False` is returned and VBScript error 5017 is raised.

The `Global` property has no effect on `Test`. The method only determines presence of a match, not count.

## Remarks

- `Test` is the fastest way to check for a match when the matched text is not needed. It performs no allocations beyond the initial compile.
- Unlike `Execute`, `Test` never returns an object. It always returns a Boolean.
- `IgnoreCase` and `MultiLine` apply to the pattern used by `Test` exactly as they do for `Execute`.

## Code Example

```asp
<%
Option Explicit
Dim re
Set re = Server.CreateObject("VBScript.RegExp")
re.Pattern = "^[a-zA-Z0-9._%+\\-]+@[a-zA-Z0-9.\\-]+\\.[a-zA-Z]{2,}$"
re.IgnoreCase = True

Dim email
email = Request.Form("email")
If re.Test(email) Then
    Response.Write "Valid email address."
Else
    Response.Write "Invalid email address."
End If

Set re = Nothing
%>
```
