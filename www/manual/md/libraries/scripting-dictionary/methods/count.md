# Count Dictionary Entries

## Overview
Use Count to read how many entries are currently stored.

## Syntax

```asp
countValue = dict.Count()
```

## Parameters
- No parameters.

## Return Value
Returns an Integer containing the number of entries.

## How It Works
- Count reads the current key slice length.
- Add, Remove, RemoveAll, and Item assignment can change this value.

## Remarks
- Count is also available as property-style access: dict.Count.
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "A", 1
dict.Add "B", 2

Response.Write dict.Count()

Set dict = Nothing
%>
```

