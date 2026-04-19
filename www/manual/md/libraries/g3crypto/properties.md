# G3CRYPTO Properties

## Overview

This page lists the properties exposed by `G3CRYPTO`.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `BCryptCost` | Read/Write | Integer | bcrypt work factor used by `HashPassword`. |
| `CanReuseTransform` | Read-only | Boolean | Always `True`. |
| `Hash` | Read-only | Array | Raw bytes from the most recent digest operation that updates internal hash state. |
| `HashSize` | Read-only | Integer | Digest size in bits for the current internal hash context. |

## Remarks

- Property reads do not perform cryptographic work.
- Setting `BCryptCost` outside `4..31` is ignored.
