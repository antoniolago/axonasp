# G3ZIP Methods

## Overview

This page summarizes every method exposed by `G3ZIP` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Open(path)` | Boolean | Opens an existing ZIP archive for read mode. Returns `True` on success; otherwise `False`. |
| `Create(path)` | Boolean | Creates a ZIP archive for write mode. Returns `True` on success; otherwise `False`. |
| `AddFile(sourcePath [, nameInZip])` | Boolean | Adds one file to an archive in write mode. Returns `True` on success; otherwise `False`. |
| `AddFolder(sourcePath [, nameInZip])` | Boolean | Adds one folder recursively to an archive in write mode. Returns `True` on success; otherwise `False`. |
| `AddText(nameInZip, text)` | Boolean | Adds text content as an entry in write mode. Returns `True` on success; otherwise `False`. |
| `ExtractAll(destinationPath)` | Boolean | Extracts all entries in read mode. Returns `True` on success; otherwise `False`. |
| `ExtractFile(nameInZip, destinationPath)` | Boolean | Extracts one entry in read mode. Returns `True` on success; otherwise `False`. |
| `List()` | Array | Returns an array of entry names from the open archive. |
| `GetInfo(nameInZip)` | Scripting.Dictionary or Empty | Returns metadata dictionary for one entry, or Empty when argument is missing or entry is not found. |
| `Close()` | Boolean | Closes archive resources and returns `True`. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3ZIP")`.
- Method names are case-insensitive.
- Write operations require write mode; read/extract operations require read mode.
