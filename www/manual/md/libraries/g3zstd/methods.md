# G3ZSTD Methods

## Overview
This page summarizes the methods available in the G3ZSTD library for Zstandard compression and decompression in G3Pix AxonASP.

## Methods Reference

| Method | Returns | Description |
|---|---|---|
| SetLevel | Boolean | Sets the default compression level for the instance. |
| Compress | Byte Array or Empty | Compresses a string or byte array payload and returns compressed bytes. Returns Empty when input is invalid or compression fails. |
| Decompress | Byte Array or Empty | Decompresses a compressed payload and returns original bytes. Returns Empty when payload is invalid or decompression fails. |
| DecompressText | String | Decompresses a payload and converts the result to UTF-8 text. Returns an empty string on failure. |
| CompressMany | Array of Byte Arrays | Compresses each item from an input array. Returns an empty array when one of the items is invalid. |
| DecompressMany | Array of Byte Arrays | Decompresses each item from an input array. Returns an empty array when one of the items is invalid. |
| CompressFile | Boolean | Compresses a source file to a target file path. |
| DecompressFile | Boolean | Decompresses a source file to a target file path. |
| Clear | Boolean | Releases internal encoder and decoder state and clears the last error. |

## Remarks
- Method names are case-insensitive.
- Valid compression levels are from -5 to 22.
- After operational errors, inspect LastError.
