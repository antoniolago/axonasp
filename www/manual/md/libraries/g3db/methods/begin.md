# Begin a Transaction

## Overview

Starts a database transaction using default options.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set tx = db.Begin()
```

## Parameters

None.

## Return Value

- **G3DBTransaction**: Returned when transaction start succeeds.
- **Empty**: Returned when connection is not open or transaction creation fails.

## Remarks

- Aliases `BeginTrans` and `BeginTransaction` call the same runtime path.

## Example

```asp
<%
Option Explicit
Dim db, tx
Set db = Server.CreateObject("G3DB")

If db.Open("mysql", "user:pass@tcp(localhost)/db") Then
    Set tx = db.Begin()
    If Not IsEmpty(tx) Then tx.Rollback
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Begin`
- **Arguments**: none
- **Returns**: G3DBTransaction on success, Empty on failure
