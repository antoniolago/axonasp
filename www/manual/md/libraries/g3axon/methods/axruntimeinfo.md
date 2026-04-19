# Get Runtime Diagnostic Report

## Overview

Returns a multi-section diagnostic report covering runtime details, server context, a memory snapshot, all loaded configuration keys from `config/axonasp.toml`, and the AxonASP legal attribution block.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxRuntimeInfo()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **String**: A plain-text diagnostic report. The format mirrors a `phpinfo()`-style output and is intended to be wrapped in a `<pre>` element for display.

## Remarks

- Only expose this method on secured administrative pages. The report includes internal configuration values.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, report
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

report = ax.AxRuntimeInfo()
Response.Write "<pre>" & Server.HTMLEncode(report) & "</pre>"

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxRuntimeInfo`
- **Arguments**: None
- **Returns**: String — multi-section plain-text diagnostic report
```