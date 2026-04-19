# G3DB Properties

## Overview

This page lists the properties exposed by `G3DB`.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `Driver` | Read/Write | String | Normalized database driver name used by the connection object. |
| `DSN` | Read/Write | String | Current connection string stored in the object. |
| `IsOpen` | Read-only | Boolean | Indicates whether the database pool is currently open. |
| `LastError` | Read-only | String | Latest error text recorded by the object. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3DB")`.
- `Driver` and `DSN` can be assigned before opening a connection.
