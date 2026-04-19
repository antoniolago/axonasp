# Validate an Email Address

## Overview

Determines whether a string is a syntactically valid email address.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxFilterValidateEmail(emailAddress)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **emailAddress** | String | Yes | The string to validate as an email address. |

## Return Value

- **Boolean `True`**: The string is a syntactically valid email address.
- **Boolean `False`**: The string is not a valid email address, or no argument was supplied.

## Remarks

- Validation uses Go's `mail.ParseAddress`, which checks RFC 5322 syntax. It does not perform DNS MX record lookups or verify the mailbox exists.
- Addresses with display names (e.g., `John Doe <john@example.com>`) are accepted.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

If ax.AxFilterValidateEmail("user@example.com") Then
    Response.Write "user@example.com is valid.<br>"
End If

If Not ax.AxFilterValidateEmail("not-an-email") Then
    Response.Write "not-an-email is invalid.<br>"
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxFilterValidateEmail`
- **Arguments**: `emailAddress` (String, required)
- **Returns**: Boolean — `True` if syntactically valid email; `False` otherwise
