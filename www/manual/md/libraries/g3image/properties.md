# G3IMAGE Properties

## Overview

This page lists the properties exposed by `G3IMAGE`.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `HasContext` | Read-only | Boolean | Indicates whether an active drawing context exists. |
| `Width` | Read-only | Integer | Pixel width of the active drawing context, or `0` when no context exists. |
| `Height` | Read-only | Integer | Pixel height of the active drawing context, or `0` when no context exists. |
| `LastError` | Read-only | String | Latest operation error message. |
| `LastMimeType` | Read-only | String | MIME type of the most recent rendered output. |
| `LastTempFile` | Read-only | String | Temporary file path used by the most recent temp render operation. |
| `LastBytes` | Read-only | Array | Byte array from the most recent render operation. |
| `DefaultFormat` | Read/Write | String | Default render format (`png`, `jpg`, or `jpeg`). |
| `JPGQuality` | Read/Write | Integer | JPEG quality setting clamped to the range `1..100`. |
| `AlignLeft` | Read-only | Integer | Drawing constant for left text alignment. |
| `AlignCenter` | Read-only | Integer | Drawing constant for centered text alignment. |
| `AlignRight` | Read-only | Integer | Drawing constant for right text alignment. |
| `FillRuleWinding` | Read-only | Integer | Drawing constant for winding fill rule. |
| `FillRuleEvenOdd` | Read-only | Integer | Drawing constant for even-odd fill rule. |
| `LineCapRound` | Read-only | Integer | Drawing constant for round line caps. |
| `LineCapButt` | Read-only | Integer | Drawing constant for butt line caps. |
| `LineCapSquare` | Read-only | Integer | Drawing constant for square line caps. |
| `LineJoinRound` | Read-only | Integer | Drawing constant for round line joins. |
| `LineJoinBevel` | Read-only | Integer | Drawing constant for bevel line joins. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3IMAGE")`.
- Property names are case-insensitive.
