# Set Dictionary CompareMode

## Overview
Use CompareMode to control how keys are compared during lookup and existence checks.

## Syntax

```asp
mode = dict.CompareMode
dict.CompareMode = modeValue
```

## Parameters
- modeValue (Integer, required for assignment):
  - `0` = BinaryCompare (case-sensitive)
  - `1` = TextCompare (case-insensitive)

## Return Value
Getter returns an Integer representing the current comparison mode.

Setter returns no value.

## How It Works
- CompareMode changes key normalization rules used by Exists, Item, Add, Remove, and Key.
- CompareMode can be changed only while the dictionary is empty.

## Remarks
- Assigning CompareMode after entries already exist raises an error.
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.CompareMode = 1
dict.Add "Token", "A"

Response.Write CStr(dict.Exists("token"))

Set dict = Nothing
%>
```

