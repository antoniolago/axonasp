# G3TEMPLATE Methods

## Overview

This page summarizes every method exposed by `G3TEMPLATE` in G3Pix AxonASP.

## Methods

| Method | Returns | Description |
|---|---|---|
| `Render(templatePath [, data])` | String | Renders a template file and returns output text; returns an error String when path is missing, template parsing fails, or template execution fails. |

## Remarks

- Instantiate the library with `Server.CreateObject("G3TEMPLATE")`.
- Method names are case-insensitive.
- Template paths are resolved through the host environment when available.
