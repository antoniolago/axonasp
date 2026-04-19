# Validate an IP Address

## Overview

Determines whether a string is a valid IPv4 or IPv6 address.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = ax.AxFilterValidateIp(ipAddress)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **ipAddress** | String | Yes | The string to validate as an IP address. |

## Return Value

- **Boolean `True`**: The string is a valid IPv4 or IPv6 address.
- **Boolean `False`**: The string is not a valid IP address, or no argument was supplied.

## Remarks

- Validation uses Go's `net.ParseIP`, which accepts both IPv4 (e.g., `192.168.1.1`) and IPv6 (e.g., `::1`) addresses.
- This method does not perform DNS resolution or reachability checks.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

If ax.AxFilterValidateIp("192.168.1.1") Then
    Response.Write "192.168.1.1 is valid.<br>"
End If

If ax.AxFilterValidateIp("::1") Then
    Response.Write "::1 is a valid IPv6 address.<br>"
End If

If Not ax.AxFilterValidateIp("not-an-ip") Then
    Response.Write "not-an-ip is invalid.<br>"
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxFilterValidateIp`
- **Arguments**: `ipAddress` (String, required)
- **Returns**: Boolean — `True` if valid IPv4 or IPv6; `False` otherwise
