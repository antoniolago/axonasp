# G3TAR Methods

## Overview

This page summarizes every method exposed by `G3TAR` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Create(path)` | Boolean | Creates a TAR archive in write mode. Returns `True` on success; otherwise `False`. |
| `Open(path)` | Boolean | Opens a TAR archive in read mode and indexes entries. Returns `True` on success; otherwise `False`. |
| `AddFile(sourcePath [, nameInTar])` | Boolean | Adds one file to archive in write mode. Returns `True` on success; otherwise `False`. |
| `AddFolder(sourcePath [, nameInTar])` | Boolean | Adds one folder recursively to archive in write mode. Returns `True` on success; otherwise `False`. |
| `AddFiles(items [, prefix])` | Boolean | Adds multiple items from array/dictionary input to archive in write mode. Returns `True` on success; otherwise `False`. |
| `AddText(nameInTar, text)` | Boolean | Adds text content as one TAR entry in write mode. Returns `True` on success; otherwise `False`. |
| `List()` | Array | Returns an array of TAR entry names. |
| `ExtractAll(destinationPath)` | Boolean | Extracts all TAR entries in read mode. Returns `True` on success; otherwise `False`. |
| `ExtractFile(nameInTar, destinationPath)` | Boolean | Extracts one TAR entry in read mode. Returns `True` on success; otherwise `False`. |
| `GetInfo(nameInTar)` | Scripting.Dictionary or Empty | Returns metadata dictionary for one entry, or Empty when argument is missing or entry is not found. |
| `Close()` | Boolean | Closes TAR resources and returns `True`. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3TAR")`.
- Method names are case-insensitive.
- Use `LastError` for failure diagnostics.
