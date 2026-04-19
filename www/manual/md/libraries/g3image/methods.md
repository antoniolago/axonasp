# G3IMAGE Methods

## Overview

This page summarizes every method exposed by `G3IMAGE` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Close()` | Boolean | Releases drawing/image resources and resets internal state. Returns `True`. |
| `NewContext(width, height)` | Boolean or Empty | Creates a new drawing context. Returns `True` on success, Empty when arguments are invalid. |
| `LoadImage(path)` | Boolean or Empty | Loads image from file using auto-decoding. Returns `True` on success, Empty on failure. |
| `LoadPNG(path)` | Boolean or Empty | Loads PNG image from file. Returns `True` on success, Empty on failure. |
| `LoadJPG(path)` | Boolean or Empty | Loads JPEG image from file. Returns `True` on success, Empty on failure. |
| `ContextForImage()` | Boolean | Creates drawing context from last loaded image. Returns `True` on success, `False` when no image is loaded. |
| `SavePNG(path)` | Boolean | Saves active context as PNG. Returns `True` on success; otherwise `False`. |
| `SaveJPG(path [, quality])` | Boolean | Saves active context as JPEG. Returns `True` on success; otherwise `False`. |
| `SetHexColor(hexColor)` | Empty | Sets current drawing color from hexadecimal value. |
| `SetColor(colorText)` | Empty | Sets current drawing color from color text value. |
| `Clear()` | Empty | Clears the active context. |
| `SetLineWidth(width)` | Empty | Sets stroke width for subsequent path operations. |
| `DrawLine(x1, y1, x2, y2)` | Empty | Adds a line path segment to the active context. |
| `DrawRectangle(x, y, width, height)` | Empty | Adds a rectangle path to the active context. |
| `DrawCircle(x, y, radius)` | Empty | Adds a circle path to the active context. |
| `DrawEllipse(x, y, rx, ry)` | Empty | Adds an ellipse path to the active context. |
| `Stroke()` | Empty | Strokes the current path. |
| `Fill()` | Empty | Fills the current path. |
| `FillPreserve()` | Empty | Fills the current path and preserves path data. |
| `StrokePreserve()` | Empty | Strokes the current path and preserves path data. |
| `LoadFontFace(path, points)` | Boolean | Loads a font face and applies it to active context when present. Returns `True` on success; otherwise `False`. |
| `DrawString(text, x, y)` | Empty | Draws text at coordinates. |
| `DrawStringAnchored(text, x, y, ax, ay)` | Empty | Draws anchored text with alignment factors. |
| `MeasureString(text)` | Array or Empty | Returns two-element array `[width, height]` as Double values, or Empty when no context is active. |
| `DrawImage(x, y)` | Empty | Draws last loaded image at destination coordinates in the active context. |
| `RenderViaTemp([format] [, quality])` | Array or Empty | Renders current image and returns byte array; returns Empty on render failure. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3IMAGE")`.
- Method names are case-insensitive.
- Inspect `LastError` when methods return `False` or Empty.
