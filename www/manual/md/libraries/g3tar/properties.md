# G3TAR Properties

## Overview

This page lists the properties exposed by `G3TAR`.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `Path` | Read-only | String | Active TAR archive path. |
| `Mode` | Read-only | String | Current mode (`r` for read or `w` for write). |
| `Count` | Read-only | Integer | Number of indexed entries in the current TAR context. |
| `LastError` | Read-only | String | Latest TAR operation error text. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3TAR")`.
