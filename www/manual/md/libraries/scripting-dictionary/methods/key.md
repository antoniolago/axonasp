# Rename a Dictionary Key

## Overview
Use Key to rename an existing dictionary key without changing its associated value.

## Syntax

```asp
dict.Key(oldKey) = newKey
```

## Parameters
- oldKey (Variant, required): Existing key to rename.
- newKey (Variant, required): New key name.

## Return Value
Returns Empty.

## How It Works
- The key position is preserved in insertion order.
- Renaming fails when oldKey does not exist.
- Renaming fails when newKey already exists.

## Remarks
- Runtime assignment syntax is the recommended form.
- Member names are case-insensitive.

## Example

```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "OldName", "Value"
dict.Key("OldName") = "NewName"

Response.Write dict.Item("NewName")

Set dict = Nothing
%>
```

