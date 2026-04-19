# G3TESTSUITE Properties

## Overview

This page lists the properties exposed by `G3TESTSUITE`.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `Suite` | Read/Write | String | Current suite/describe label for assertion diagnostics. |
| `CurrentDescribe` | Read/Write | String | Alias of `Suite` for describe label access. |
| `Total` | Read-only | Integer | Total number of assertions executed. |
| `Passed` | Read-only | Integer | Number of successful assertions. |
| `Failed` | Read-only | Integer | Number of failed assertions. |
| `HasFailures` | Read-only | Boolean | `True` when one or more failures are recorded. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3TESTSUITE")`.
- `Suite` and `CurrentDescribe` map to the same runtime field.
