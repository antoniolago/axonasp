# Parse a CSV Row String

## Overview

Parses one CSV-formatted row string and returns its fields as a zero-based VBArray.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
arr = obj.AxStringGetCSV(str [, delimiter])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | A single CSV row string to parse. Quoted fields and embedded delimiters are handled correctly. |
| delimiter | String | Optional | The field separator character. Only the first character in the string is used. Defaults to `,`. |

## Return Value

- **Array**: Returns a zero-based VBArray of String fields parsed from `str`.
- **Array**: Returns an empty array when no argument is provided or when parsing fails.

## Remarks

- Only the first row of a multi-row CSV string is parsed.
- Quoted fields with embedded commas are handled correctly by the underlying CSV parser.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, fields
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

fields = ax.AxStringGetCSV("apple,\"banana,split\",cherry")
Response.Write fields(0) & "<br>" ' apple
Response.Write fields(1) & "<br>" ' banana,split
Response.Write fields(2) & "<br>" ' cherry

' Tab-delimited
fields = ax.AxStringGetCSV("col1" & Chr(9) & "col2", Chr(9))
Response.Write fields(0)          ' col1

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxStringGetCSV`
- **Arguments**: `str As String [, delimiter As String]`
- **Returns**: `Array` (zero-based VBArray of String fields)