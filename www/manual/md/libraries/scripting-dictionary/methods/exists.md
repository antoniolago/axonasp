# Check Whether a Key Exists

## Overview
Use Exists to test if a dictionary key is present.

## Syntax

```asp
found = dict.Exists(key)
```

## Parameters
- key (Variant, required): Key to test.

## Return Value
Returns Boolean True when the key exists.

Returns Boolean False when the key does not exist.

## How It Works
- Exists uses the dictionary index map and CompareMode rules.
- Missing argument raises an error in runtime validation.

## Remarks
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "Region", "US"
Response.Write CStr(dict.Exists("Region"))

Set dict = Nothing
%>
```

