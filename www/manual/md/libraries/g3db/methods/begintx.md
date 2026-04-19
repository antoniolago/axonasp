# Begin a Transaction with Options

## Overview

Starts a database transaction with optional timeout and read-only configuration.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set tx = db.BeginTx([timeoutSeconds, readOnly])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **timeoutSeconds** | Integer | No | Timeout in seconds. Use `0` or omit for no timeout. |
| **readOnly** | Boolean | No | `True` to request read-only transaction mode. |

## Return Value

- **G3DBTransaction**: Returned when transaction start succeeds.
- **Empty**: Returned when connection is not open or transaction creation fails.

## Remarks

- Timeout is only applied when `timeoutSeconds` is greater than zero.

## Example

```asp
<%
Option Explicit
Dim db, tx
Set db = Server.CreateObject("G3DB")

If db.Open("postgres", "host=localhost user=u dbname=app") Then
    Set tx = db.BeginTx(30, True)
    If Not IsEmpty(tx) Then tx.Rollback
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `BeginTx`
- **Arguments**: `timeoutSeconds` (Integer, optional), `readOnly` (Boolean, optional)
- **Returns**: G3DBTransaction on success, Empty on failure
