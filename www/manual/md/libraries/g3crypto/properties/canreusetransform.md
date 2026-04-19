# CanReuseTransform Property

## Overview

Indicates whether the crypto transform can be reused across operations.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3CRYPTO")`.

## Syntax

```asp
isReusable = crypto.CanReuseTransform
```

## Return Value

- **Boolean**: Always `True`.

## Remarks

- This property is provided for compatibility.
- It is not a runtime capability probe because the value is constant.

## API Reference

- **Object**: `G3CRYPTO`
- **Property**: `CanReuseTransform`
- **Access**: Read-only
- **Type**: Boolean (`True`)

## Code Example

```asp
<%
Option Explicit
Dim crypto
Set crypto = Server.CreateObject("G3CRYPTO")

If crypto.CanReuseTransform Then
    Response.Write "Transform is reusable"
End If

Set crypto = Nothing
%>
```
