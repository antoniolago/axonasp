# Remove a Dictionary Entry

## Overview
Use Remove to delete one dictionary entry by key.

## Syntax

```asp
dict.Remove key
```

## Parameters
- key (Variant, required): Key to remove.

## Return Value
Returns Empty.

## How It Works
- Remove deletes both key and value and rebuilds the internal index map.
- Remove raises an error when the key does not exist.

## Remarks
- Remove requires one argument.
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "Token", "ABC"
dict.Remove "Token"

Response.Write "Count=" & dict.Count

Set dict = Nothing
%>
```

