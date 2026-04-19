# Clear All Dictionary Entries

## Overview
Use RemoveAll to clear all key-value entries in the dictionary.

## Syntax

```asp
dict.RemoveAll
```

## Parameters
- No parameters.

## Return Value
Returns Empty.

## How It Works
- RemoveAll clears key and value storage.
- Count becomes 0 after completion.

## Remarks
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "A", 1
dict.Add "B", 2
dict.RemoveAll

Response.Write "Count=" & dict.Count

Set dict = Nothing
%>
```

