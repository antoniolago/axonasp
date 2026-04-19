# G3ZIP Properties

## Overview

This page lists the properties exposed by `G3ZIP`.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `Path` | Read-only | String | Full path of the active ZIP archive. |
| `Mode` | Read-only | String | Current mode (`r` for read or `w` for write). |
| `Count` | Read-only | Integer | Number of entries in the open reader archive; `0` when not in read mode. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3ZIP")`.
