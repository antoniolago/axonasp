# Execute a Query and Return One Row

## Overview

Executes a SQL query and returns a G3DBRow object for single-row scanning.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set row = db.QueryRow(sql[, params...])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **sql** | String | Yes | SQL query text. |
| **params** | Any | No | Positional values for query placeholders. |

## Return Value

- **G3DBRow**: Returned when query dispatch succeeds.
- **Empty**: Returned when connection is not open or SQL is missing.

## Remarks

- Use `Scan` or `ScanMap` on the returned row object.
- If no row is found, scan methods return Empty.

## Example

```asp
<%
Option Explicit
Dim db, row, value
Set db = Server.CreateObject("G3DB")

If db.Open("postgres", "host=localhost user=u dbname=app") Then
    Set row = db.QueryRow("SELECT name FROM users WHERE id = ?", 1)
    If Not IsEmpty(row) Then
        value = row.Scan()
        If Not IsEmpty(value) Then Response.Write value
    End If
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `QueryRow`
- **Arguments**: `sql` (String, required), `params...` (Any, optional)
- **Returns**: G3DBRow on dispatch success, Empty on connection/argument failure
