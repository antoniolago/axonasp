# G3MD Properties

## Overview
This page summarizes properties available in the G3MD library for Markdown rendering configuration.

## Properties Reference

| Property | Access | Type | Description |
|---|---|---|---|
| HardWraps | Read/Write | Boolean | When True, converts soft line breaks into HTML line breaks. |
| Unsafe | Read/Write | Boolean | When True, allows raw HTML and non-sanitized links in rendered output. |

## Remarks
- Property names are case-insensitive.
- Property values affect subsequent Process calls on the same instance.
