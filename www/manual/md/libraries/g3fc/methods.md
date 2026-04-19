# G3FC Methods

## Overview
This page summarizes the methods exposed by the G3FC archive library in G3Pix AxonASP.

## Methods Reference

| Method | Returns | Description |
|---|---|---|
| Create | Boolean | Creates a new G3FC archive from one or more source paths. |
| Extract | Boolean | Extracts all items from a G3FC archive to a target directory. |
| List | Array of Dictionary or Empty | Lists archive entries with size and path metadata. Returns Empty on invalid arguments or read failure. |
| Info | Boolean | Exports archive metadata details to an output file. |
| Find | Array of Dictionary or Empty | Searches entries by substring or regular expression and returns matching items. Returns Empty on invalid arguments or read failure. |
| ExtractSingle | Boolean | Extracts one file entry from an archive to a target path. |

## Remarks
- Method names are case-insensitive.
- ExtractSingle also accepts aliases extract-single and extract_single.
