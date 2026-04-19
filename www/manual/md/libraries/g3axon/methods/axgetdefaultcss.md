# Get the Default CSS Stylesheet Content

## Overview

Returns the text content of the CSS file configured in the `axfunctions.ax_default_css_path` setting of `config/axonasp.toml`.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

Set the CSS file path in `config/axonasp.toml`:

```toml
[axfunctions]
ax_default_css_path = "./www/css/axonasp.css"
```

## Syntax

```asp
result = ax.AxGetDefaultCss()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **String**: The raw CSS text from the configured file.
- **String (empty)**: Returned when `ax_default_css_path` is not configured or the file cannot be read.

## Remarks

- The file path is resolved relative to the AxonASP executable directory.
- This method allows ASP pages to inline the system stylesheet without hardcoding file paths.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, css
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

css = ax.AxGetDefaultCss()

If css <> "" Then
    Response.Write "<style>" & vbCrLf & css & vbCrLf & "</style>"
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxGetDefaultCss`
- **Arguments**: None
- **Returns**: String — CSS file content, or empty string if not configured or unreadable
