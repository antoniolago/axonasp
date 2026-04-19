# G3HTTP Methods

## Overview

This page summarizes every method exposed by `G3HTTP` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Fetch(url [, method] [, body])` | Dictionary, Array, scalar, String, or Empty | Sends an outbound HTTP request. Returns parsed JSON-native values when JSON parsing succeeds, raw response String when response is non-JSON or JSON parse fails, and Empty on request/IO failures. |
| `Request(url [, method] [, body])` | Dictionary, Array, scalar, String, or Empty | Alias of `Fetch` with the same runtime behavior and return contract. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3HTTP")`.
- Method names are case-insensitive.
- Default timeout is 10 seconds per request.
