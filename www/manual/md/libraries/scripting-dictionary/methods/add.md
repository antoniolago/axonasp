# Add a Dictionary Entry

## Overview
Use Add to insert a new key-value pair into the dictionary.

## Syntax

```asp
dict.Add key, value
```

## Parameters
- key (Variant, required): Entry key.
- value (Variant, required): Entry value.

## Return Value
Returns Empty.

## How It Works
- Add inserts the key and value at the end of insertion order.
- If the key already exists, Add raises an error and does not overwrite the value.

## Remarks
- Add requires exactly two arguments.
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "Language", "VBScript"
Response.Write dict.Item("Language")

Set dict = Nothing
%>
```

