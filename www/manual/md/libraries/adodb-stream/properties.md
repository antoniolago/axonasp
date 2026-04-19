# ADODB.Stream Properties Reference

## Overview

Use these properties to control encoding, cursor location, and stream metadata.

## Properties

| Property | Access | Type | Description |
|---|---|---|---|
| **Type** | Read/Write | Integer | Stream type (`1` binary, `2` text). |
| **Mode** | Read/Write | Integer | Mode flag value. |
| **State** | Read | Integer | Stream state (`0` closed, `1` open). |
| **Position** | Read/Write | Integer | Current cursor position in bytes. |
| **Size** | Read | Integer | Current stream size in bytes. |
| **Charset** | Read/Write | String | Text encoding name used by `ReadText` and `WriteText`. |
| **LineSeparator** | Read/Write | Integer | Line separator flag used when `WriteText` is called with append-line option. |
| **EOS** | Read | Boolean | `True` when `Position >= Size`. |

## How It Works

- Assigning `Position` clamps values to the valid range `0` to `Size`.
- `Charset` defaults to `unicode` for new stream objects.
- `Size` changes after write, load, copy, or truncation operations.

## Remarks

- Property names are case-insensitive.
- Assigning an empty `Charset` resets it to `utf-8` in the current runtime.
- `EOS` is computed from `Position` and `Size`, and cannot be assigned directly.

