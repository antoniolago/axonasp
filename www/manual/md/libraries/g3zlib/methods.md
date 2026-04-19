# G3ZLIB Methods

## Overview

This page summarizes every method exposed by `G3ZLIB` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Compress(input [, level])` | Array or Empty | Compresses text or byte-array input and returns compressed bytes as an array; returns Empty when input is missing or compression fails. |
| `Decompress(input)` | Array or Empty | Decompresses byte-array input and returns decompressed bytes as an array; returns Empty on missing input or decompression failure. |
| `DecompressText(input)` | String | Decompresses input and returns UTF-8 text; returns empty string when input is missing or conversion fails. |
| `CompressMany(items [, level])` | Array | Compresses each item from input array and returns an array of compressed byte arrays; returns empty array when input is missing or any item compression fails. |
| `DecompressMany(items)` | Array | Decompresses each item from input array and returns an array of decompressed byte arrays. |
| `CompressFile(sourcePath, destPath [, level])` | Boolean | Compresses one file to destination path. Returns `True` on success; otherwise `False`. |
| `DecompressFile(sourcePath, destPath)` | Boolean | Decompresses one file to destination path. Returns `True` on success; otherwise `False`. |
| `Clear()` | Boolean | Clears last error state and returns `True`. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3ZLIB")`.
- Method names are case-insensitive.
- Use `LastError` for failure diagnostics.
