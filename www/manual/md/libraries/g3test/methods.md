# G3TESTSUITE Methods

## Overview

This page summarizes every method exposed by `G3TESTSUITE` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `AssertEqual(expected, actual [, message])` | Boolean | Returns `True` when values are equal under VM comparison semantics; otherwise `False`. |
| `AssertNotEqual(expected, actual [, message])` | Boolean | Returns `True` when values are not equal; otherwise `False`. |
| `AssertTrue(condition [, message])` | Boolean | Returns `True` when condition evaluates to true; otherwise `False`. |
| `AssertFalse(condition [, message])` | Boolean | Returns `True` when condition evaluates to false; otherwise `False`. |
| `AssertEmpty(value [, message])` | Boolean | Returns `True` when value is Empty; otherwise `False`. |
| `AssertNull(value [, message])` | Boolean | Returns `True` when value is Null; otherwise `False`. |
| `AssertNothing(value [, message])` | Boolean | Returns `True` when value is Nothing; otherwise `False`. |
| `AssertTypeName(value, expectedTypeName [, message])` | Boolean | Returns `True` when `TypeName(value)` matches expected type name; otherwise `False`. |
| `AssertLength(value, expectedLength [, message])` | Boolean | Returns `True` when length/count matches expected value; otherwise `False`. |
| `AssertRaises(code [, expected] [, message])` | Boolean | Executes code and returns `True` when an expected error condition is met; otherwise `False`. |
| `Fail([message])` | Boolean | Records an explicit failure and returns `False`. |
| `Describe(label)` | Empty | Sets current suite/describe label used in failure diagnostics. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3TESTSUITE")`.
- Method names are case-insensitive.
- Assertion methods update `Total`, `Passed`, and `Failed` counters.
