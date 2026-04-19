# List All Environment Variables

## Overview

Returns a snapshot of all environment variables currently defined in the process as a VBArray.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

## Syntax

```asp
result = obj.AxEnvironmentList()
```

## Parameters

This method does not require parameters.

## Return Value

- **Array**: Returns a zero-based VBArray of String values, each in `KEY=VALUE` format.

## Remarks

- Pseudo-environment entries (such as entries starting with `=` on Windows) are filtered out automatically.
- The order of elements depends on the operating system.
- Method names are case-insensitive in VBScript dispatch.

## Example

```asp
<%
Option Explicit
Dim ax, envList, i
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

envList = ax.AxEnvironmentList()
For i = 0 To UBound(envList)
    Response.Write Server.HTMLEncode(envList(i)) & "<br>"
Next

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxEnvironmentList`
- **Arguments**: none
- **Returns**: `Array` (zero-based VBArray of `KEY=VALUE` strings)
