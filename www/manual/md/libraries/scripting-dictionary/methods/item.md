# Get or Set a Dictionary Item

## Overview
Use Item to read or assign a value by key.

## Syntax

```asp
value = dict.Item(key)
dict.Item(key) = value
```

## Parameters
- key (Value, required): Entry key.
- value (Value, required in assignment form): Value assigned when using set form.

## Return Value
With one argument, returns the stored value for key.

When key does not exist in get form, Item returns Empty and creates the key with Empty value.

With assignment form, Item returns Empty.

## How It Works
- Lookup respects CompareMode.
- Assignment updates existing keys or creates new keys.

## Remarks
- Member names are case-insensitive.
- The same behavior is available through default-index syntax: `dict(key)`.

## Example

```asp
<%
Option Explicit

Dim dict, missingValue
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Item("Mode") = "Production"
missingValue = dict.Item("UndefinedKey")

Response.Write "Mode=" & dict.Item("Mode") & "<br>"
Response.Write "Missing is empty=" & CStr(IsEmpty(missingValue))

Set dict = Nothing
%>
```

