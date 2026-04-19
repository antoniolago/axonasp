# Scripting.Dictionary Methods

## Overview
This page summarizes methods exposed by Scripting.Dictionary in G3Pix AxonASP.

## Methods Reference

| Method | Returns | Description |
|---|---|---|
| Add(key, value) | Empty | Adds a new entry. Raises an error when the key already exists or required arguments are missing. |
| Exists(key) | Boolean or Empty | Returns True when the key exists, False when it does not. Returns Empty after argument-count error handling. |
| Remove(key) | Empty | Removes one key. Raises an error when the key does not exist or required arguments are missing. |
| RemoveAll() | Empty | Clears all keys and values. |
| Keys() | Array | Returns a zero-based Variant array containing keys in insertion order. |
| Items() | Array | Returns a zero-based Variant array containing values in insertion order. |
| Item(key [, value]) | Value or Empty | With key only, returns the item value and auto-creates missing keys with Empty. With key and value, assigns and returns Empty. |
| Key(oldKey, newKey) | Empty | Renames an existing key. Raises an error when oldKey is missing, oldKey is not found, or newKey already exists. |
| Count() | Integer | Returns the number of dictionary entries. |

## Remarks
- Method names are case-insensitive.
- Item and Key also participate in assignment syntax patterns used by VBScript code.
