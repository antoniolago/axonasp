# Fetch the Content of a Remote URL

## Overview

Performs a synchronous HTTP GET request to a URL and returns the response body as a string.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxGetRemoteFile(url)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **url** | String | Yes | The fully qualified URL to request. Must begin with `http://` or `https://`. |

## Return Value

- **String**: The response body when the server returns HTTP 200 OK.
- **Boolean `False`**: Returned when the URL does not start with `http://` or `https://`, the request times out, a network error occurs, or the server returns a non-200 status code.

## Remarks

- The default request timeout is 10 seconds.
- No request headers, authentication, or POST body are supported. For advanced HTTP scenarios, use the `G3HTTP` library.
- Check the return type with `VarType` or `TypeName` before using the result to handle failures gracefully.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, content
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

content = ax.AxGetRemoteFile("https://example.com/api/data.json")

If VarType(content) = vbString Then
    Response.Write Server.HTMLEncode(content)
Else
    Response.Write "Failed to fetch the remote file."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxGetRemoteFile`
- **Arguments**: `url` (String, required)
- **Returns**: String (response body on HTTP 200) or Boolean `False` on failure
