# Send an HTTP Request with Request

## Overview

Executes an outbound HTTP request and returns parsed JSON content or raw response text.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3HTTP")`.

## Syntax

```asp
result = http.Request(url[, method][, body])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **url** | String | Yes | Absolute request URL. |
| **method** | String | No | HTTP method. Default is `GET`. |
| **body** | String | No | Request payload. When present, `Content-Type` is set to `application/json`. |

## Return Value

- **Scripting.Dictionary**: Returned when response content type is JSON and the root is an object.
- **Array**: Returned when response content type is JSON and the root is an array.
- **String / Integer / Double / Boolean / Null**: Returned when response content type is JSON and the root is a primitive that parses successfully.
- **String**: Raw response body for non-JSON responses.
- **String**: Raw response body when content type is JSON but parsing fails.
- **Empty**: Returned when URL is missing, request creation fails, request execution fails, or response read fails.

## Remarks

- `Request` and `Fetch` share the same runtime behavior.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim http, result
Set http = Server.CreateObject("G3HTTP")

result = http.Request("https://api.example.com/health")
If Not IsEmpty(result) Then
    Response.Write result
End If

Set http = Nothing
%>
```

## API Reference

- **Object**: `G3HTTP`
- **Method**: `Request`
- **Arguments**: `url` (String, required), `method` (String, optional), `body` (String, optional)
- **Returns**: Dictionary, Array, scalar primitive, raw response String, or Empty on request failure
