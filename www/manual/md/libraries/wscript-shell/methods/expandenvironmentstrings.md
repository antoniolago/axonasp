# Expand Environment Variables in Text

## Overview
Use ExpandEnvironmentStrings to replace tokens in the format %NAME% with values from the current process environment.

## Syntax

```asp
expanded = shell.ExpandEnvironmentStrings(inputText)
```

## Parameters

- inputText (String, required): Text that may contain one or more %NAME% placeholders.

## Return Value

Returns a String containing the expanded text.

Returns an empty string when inputText is missing.

## How It Works

- Each %NAME% token is resolved using the current environment.
- Unknown variables are preserved as written, for example %UNKNOWN_VAR% remains unchanged.

## Remarks

- Method names are case-insensitive.
- Expansion follows percent-delimited placeholder format only.

## Example

```asp
<%
Option Explicit

Dim shell, expanded
Set shell = Server.CreateObject("WScript.Shell")

expanded = shell.ExpandEnvironmentStrings("PATH=%PATH%")
Response.Write expanded

Set shell = Nothing
%>
```

