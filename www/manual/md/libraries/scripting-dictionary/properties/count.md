# Get Dictionary Entry Count

## Overview
Use Count to retrieve the current number of entries in a Scripting.Dictionary instance.

## Syntax

```asp
countValue = dict.Count
countValue = dict.Count()
```

## Parameters
- Getter only. This member accepts no arguments.

## Return Value
Returns an Integer equal to the number of entries currently stored.

## How It Works
- Count reflects the number of keys in the dictionary.
- The value updates immediately after Add, Remove, RemoveAll, and Item assignment that creates new keys.

## Remarks
- Count is exposed both as property-style and method-style access.
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "A", 10
dict.Add "B", 20

Response.Write "Count=" & dict.Count

Set dict = Nothing
%>
```

