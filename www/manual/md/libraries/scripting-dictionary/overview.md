# Use Scripting.Dictionary in G3Pix AxonASP

## Overview
Use Scripting.Dictionary to store key-value pairs with ordered keys and fast key lookup.

## Prerequisites
- Create the object with the primary ProgID Scripting.Dictionary.
- Use consistent key types when possible to keep lookups predictable.

## Syntax
```asp
Set dict = Server.CreateObject("Scripting.Dictionary")
```

## Parameters and Arguments
- ProgID (String, required): Scripting.Dictionary.

## Return Value
`Server.CreateObject("Scripting.Dictionary")` returns an object reference to a new, empty dictionary.

## How It Works
- Keys are preserved in insertion order for Keys and Items enumeration.
- CompareMode controls key normalization:
  - `0` = BinaryCompare (case-sensitive)
  - `1` = TextCompare (case-insensitive)
- Reading a missing key through Item creates that key with Empty value.

## Remarks
- Member names are case-insensitive.
- The object supports both property and method access patterns used by classic VBScript dictionary code.

## Code Example
```asp
<%
Option Explicit

Dim dict
Set dict = Server.CreateObject("Scripting.Dictionary")

dict.Add "Name", "AxonASP"
dict.Item("Version") = "2"

Response.Write "Count=" & dict.Count & "<br>"
Response.Write "Name=" & dict.Item("Name") & "<br>"
Response.Write "Version=" & dict.Item("Version")

Set dict = Nothing
%>
```

