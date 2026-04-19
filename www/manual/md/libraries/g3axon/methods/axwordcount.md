# Count Words in a String

## Overview

Counts the number of words in a string, or optionally returns an array of those words.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxWordCount(str [, format])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| str | String | Yes | The string to analyze. |
| format | Integer | Optional | Output mode. `0` (default) returns the word count as an Integer. `1` returns a zero-based VBArray of String words. |

## Return Value

- **Integer**: Returns the number of whitespace-delimited words when `format` is `0` or omitted.
- **Array**: Returns a zero-based VBArray of String words when `format` is `1`.
- **Integer**: Returns `0` when no argument is provided.

## Remarks

- Word boundaries are determined by whitespace (spaces, tabs, newlines).
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, wordArr, i
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

' Count words
Response.Write ax.AxWordCount("The quick brown fox")
' Output: 4

' Get word array
wordArr = ax.AxWordCount("Hello World ASP", 1)
For i = 0 To UBound(wordArr)
    Response.Write wordArr(i) & "<br>"
Next
' Output:
' Hello
' World
' ASP

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxWordCount`
- **Arguments**: `str As String [, format As Integer]`
- **Returns**: `Integer` (word count) or `Array` (word list when format=1)
