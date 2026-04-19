# Enumerate Dictionary Keys

## Overview
Use Keys to retrieve all dictionary keys as an array.

## Syntax

```asp
keys = dict.Keys()
```

## Parameters
- No parameters.

## Return Value
Returns a zero-based Variant array containing keys in insertion order.

## How It Works
- Keys are copied from dictionary internal key order.
- The returned array length equals Count.

## Remarks
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict, keys, i
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "A", "x"
dict.Add "B", "y"
keys = dict.Keys()

For i = 0 To UBound(keys)
    Response.Write "Key(" & i & ")=" & keys(i) & "<br>"
Next

Set dict = Nothing
%>
```

