# Scripting.Dictionary Properties

## Overview
This page summarizes properties exposed by Scripting.Dictionary in G3Pix AxonASP.

## Properties Reference

| Property | Access | Type | Description |
|---|---|---|---|
| Count | Read-only | Integer | Returns the number of key-value entries currently stored. |
| CompareMode | Read/Write | Integer | Gets or sets key comparison mode: 0 for case-sensitive comparison, 1 for case-insensitive comparison. |

## Remarks
- Property names are case-insensitive.
- Set CompareMode before adding entries. Changing CompareMode after the dictionary contains items raises an error.
