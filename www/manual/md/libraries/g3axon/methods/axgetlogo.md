# Get the Default Logo as a Base64 Data URI

## Overview

Returns the server's configured default logo image as an inline Base64 data URI string, ready for use in an HTML `<img>` tag.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

Set the logo file path in `config/axonasp.toml`:

```toml
[axfunctions]
ax_default_logo_path = "./www/images/logo.png"
```

## Syntax

```asp
result = ax.AxGetLogo()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **String**: A data URI in the form `data:{mime};base64,{base64content}` where `{mime}` is the detected MIME type (e.g., `image/png`) and `{base64content}` is the Base64-encoded file content.
- **String (empty)**: Returned when `ax_default_logo_path` is not configured or the file cannot be read.

## Remarks

- The MIME type is detected from the file extension. Supported extensions include `.png`, `.jpg`, `.gif`, `.svg`, and `.ico`.
- The file path is resolved relative to the AxonASP executable directory.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, logoUri
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

logoUri = ax.AxGetLogo()

If logoUri <> "" Then
    Response.Write "<img src=""" & logoUri & """ alt=""Logo"">"
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxGetLogo`
- **Arguments**: None
- **Returns**: String — `data:{mime};base64,{content}` URI, or empty string if not configured or unreadable