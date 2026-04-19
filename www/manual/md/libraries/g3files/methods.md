# G3FILES Methods

## Overview

This page summarizes every method exposed by `G3FILES` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Exists(path)` | Boolean | Returns `True` when the file or directory exists; otherwise `False`. |
| `Read(path [, encoding])` | String | Returns file text decoded with the requested encoding; returns empty string when path is missing or read fails. |
| `Write(path, content [, encoding] [, lineEnding] [, includeBOM])` | Boolean | Writes content to file (overwrite mode). Returns `True` on success; otherwise `False`. |
| `Append(path, content [, encoding] [, lineEnding])` | Boolean | Appends content to file (create if missing). Returns `True` on success; otherwise `False`. |
| `Delete(path)` | Boolean | Removes a file or directory entry. Returns `True` on success; otherwise `False`. |
| `Copy(sourcePath, destPath)` | Boolean | Copies source file to destination path. Returns `True` on success; otherwise `False`. |
| `Move(sourcePath, destPath)` | Boolean | Moves or renames source path to destination path. Returns `True` on success; otherwise `False`. |
| `Size(path)` | Integer | Returns file size in bytes, or `0` when path is missing, file does not exist, or path is a directory. |
| `Mkdir(path)` | Boolean | Creates directory path recursively. Returns `True` on success; otherwise `False`. |
| `List(path)` | Array | Returns a VBScript array of file names in the directory; returns an empty array when path is missing or directory read fails. |
| `NormalizeEOL(text, style)` | String | Returns text with normalized line endings (`windows`, `mac`, or `linux` style aliases). |
| `ConvertTextEncoding(text, sourceEncoding, destEncoding)` | String | Returns converted text; returns empty string when required arguments are missing. |
| `ConvertFileEncoding(sourcePath, destPath, sourceEncoding, destEncoding [, lineEnding] [, includeBOM])` | Boolean | Converts file encoding and optionally line endings/BOM. Returns `True` on success; otherwise `False`. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3FILES")`.
- Method names are case-insensitive.
- Operations are sandbox-path aware and resolve through the runtime host.
