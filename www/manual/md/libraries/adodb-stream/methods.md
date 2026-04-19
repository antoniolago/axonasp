# ADODB.Stream Methods Reference

## Overview

Use these methods to operate on text and binary stream buffers in G3Pix AxonASP.

## Methods

| Method | Syntax | Parameters | Return Value |
|---|---|---|---|
| **Open** | `stm.Open` | none | **Empty** |
| **Close** | `stm.Close` | none | **Empty** |
| **Read** | `data = stm.Read([numBytes])` | `numBytes As Integer` (Optional) | **String** containing binary byte-string data |
| **ReadText** | `text = stm.ReadText([numChars])` | `numChars As Integer` (Optional) | **String** |
| **Write** | `stm.Write data` | `data As String` (Required, treated as byte-string payload) | **Empty** |
| **WriteText** | `stm.WriteText text [, writeLine]` | `text As String` (Required), `writeLine As Integer` (Optional, `1` appends line separator) | **Empty** |
| **LoadFromFile** | `stm.LoadFromFile path` | `path As String` (Required) | **Empty** |
| **SaveToFile** | `stm.SaveToFile path [, options]` | `path As String` (Required), `options As Integer` (Optional; `1` create-new, `2` overwrite/default) | **Empty** |
| **CopyTo** | `stm.CopyTo destination [, count]` | `destination As ADODB.Stream` (Required), `count As Integer` (Optional) | **Empty** |
| **Flush** | `stm.Flush` | none | **Empty** (compatibility no-op) |
| **SetEOS** | `stm.SetEOS` | none | **Empty** |
| **SkipLine** | `stm.SkipLine` | none | **Empty** |

## How It Works

- `Read` and `ReadText` advance `Position` by the amount consumed.
- `CopyTo` copies from the current source position and advances source position.
- `SetEOS` truncates stream data at the current `Position`.

## Remarks

- `ReadText` returns an empty string when the stream is closed or at end-of-stream.
- `Write` and `WriteText` do nothing when the stream is closed.
- Charset-aware text behavior follows the current `Charset` property.

## Example

```asp
<%
Option Explicit
Dim sourceStm, targetStm

Set sourceStm = Server.CreateObject("ADODB.Stream")
Set targetStm = Server.CreateObject("ADODB.Stream")

sourceStm.Type = 2
sourceStm.Charset = "utf-8"
sourceStm.Open
sourceStm.WriteText "Line 1"
sourceStm.WriteText "Line 2", 1
sourceStm.Position = 0

targetStm.Type = 2
targetStm.Charset = "utf-8"
targetStm.Open
sourceStm.CopyTo targetStm

targetStm.Position = 0
Response.Write targetStm.ReadText()

sourceStm.Close
targetStm.Close
Set sourceStm = Nothing
Set targetStm = Nothing
%>
```

