# Enumerate Dictionary Values

## Overview
Use Items to retrieve all stored values as an array.

## Syntax

```asp
values = dict.Items()
```

## Parameters
- No parameters.

## Return Value
Returns a zero-based Variant array containing dictionary values in insertion order.

## How It Works
- The returned array length equals Count.
- Values are copied from the dictionary storage order.

## Remarks
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict, values, i
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "A", 10
dict.Add "B", 20
values = dict.Items()

For i = 0 To UBound(values)
    Response.Write "Value(" & i & ")=" & values(i) & "<br>"
Next

Set dict = Nothing
%>
```

