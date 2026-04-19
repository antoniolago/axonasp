# Read Database Pool Statistics

## Overview

Returns runtime pool statistics for the active G3DB connection.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set stats = db.Stats()
```

## Parameters

None.

## Return Value

- **Scripting.Dictionary**: Returned when connection is open.
- **Empty**: Returned when connection is not open.

## Remarks

- Dictionary keys include `MaxOpenConnections`, `OpenConnections`, `InUse`, `Idle`, `WaitCount`, `WaitDurationSeconds`, `MaxIdleClosed`, `MaxIdleTimeClosed`, and `MaxLifetimeClosed`.

## Example

```asp
<%
Option Explicit
Dim db, stats
Set db = Server.CreateObject("G3DB")

If db.Open("mysql", "user:pass@tcp(localhost)/db") Then
  Set stats = db.Stats()
  If IsObject(stats) Then Response.Write stats("OpenConnections")
  db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Stats`
- **Arguments**: none
- **Returns**: Scripting.Dictionary on open connection, Empty otherwise
