# G3DB Methods

## Overview

This page summarizes every method exposed by `G3DB` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Begin()` | G3DBTransaction or Empty | Starts a transaction with default options. Returns Empty when connection is not open or transaction start fails. |
| `BeginTx([timeoutSeconds, readOnly])` | G3DBTransaction or Empty | Starts a transaction with optional timeout/read-only flags. Returns Empty on failure. |
| `Close()` | Boolean | Returns True on successful close or when already closed; False when close returns an error. |
| `Exec(sql [, params...])` | G3DBResult or Empty | Executes a non-query statement. Returns Empty when connection is not open, SQL is missing, or execution fails. |
| `GetError()` | String | Returns the current error message, or empty string when no error is stored. |
| `Open(driver, dsn)` | Boolean | Returns True when open and ping validation succeed; otherwise False. |
| `OpenFromEnv([driver])` | Boolean | Opens using configuration/env values. Returns True on success; otherwise False. |
| `Prepare(sql)` | G3DBStatement or Empty | Creates a prepared statement. Returns Empty on connection/argument/prepare failure. |
| `Query(sql [, params...])` | G3DBResultSet or Empty | Executes a query and returns a forward-only result set. Returns Empty on failure. |
| `QueryRow(sql [, params...])` | G3DBRow or Empty | Executes a query and returns a single-row object for scan methods. Returns Empty on connection or argument failure. |
| `SetConnMaxIdleTime(seconds)` | Empty | Sets pool idle timeout when connection is open. |
| `SetConnMaxLifetime(seconds)` | Empty | Sets maximum pool connection lifetime when connection is open. |
| `SetMaxIdleConns(count)` | Empty | Sets maximum idle pooled connections when connection is open. |
| `SetMaxOpenConns(count)` | Empty | Sets maximum open pooled connections when connection is open. |
| `Stats()` | Scripting.Dictionary or Empty | Returns current pool statistics dictionary when connection is open; otherwise Empty. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3DB")`.
- Method names are case-insensitive.
- Error details are available through `LastError` and `GetError()`.
