# G3JSON Methods

## Overview

This page summarizes every method exposed by `G3JSON` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `LoadFile(path)` | Dictionary, Array, scalar, Null, or Empty | Reads JSON from a file path and parses it to native values; returns Empty when path is missing, read fails, or JSON is invalid. |
| `NewArray()` | Array | Creates an empty VBScript array for JSON composition. |
| `NewObject()` | Scripting.Dictionary | Creates an empty dictionary object for JSON composition. |
| `Parse(jsonText)` | Dictionary, Array, scalar, Null, or Empty | Parses JSON text to native values; returns Empty when input is missing, empty, or invalid. |
| `Stringify(value)` | String | Serializes a native value to JSON text; returns empty string when argument is missing or serialization fails. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3JSON")`.
- Method names are case-insensitive.
- Parsing methods return Empty on operational failure.
